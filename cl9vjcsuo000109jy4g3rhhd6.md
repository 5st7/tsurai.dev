# 【Golang】exec.Commandを使って別ユーザーの権限でコマンドを実行したい

サンプルコード

```golang
package main

import (
	"fmt"
	"os/exec"
	"os/user"
	"strconv"
	"syscall"
)

func main() {
    username := "test"
	u, _ := user.Lookup(username)

        uid, _ := strconv.Atoi(u.Uid)
        gid, _ := strconv.Atoi(u.Gid)

	cmd := exec.Command("whoami")
	cmd.SysProcAttr = &syscall.SysProcAttr{}
	cmd.SysProcAttr.Credential = &syscall.Credential{Uid: uint32(uid), Gid: uint32(gid)}
	out, _ := cmd.Output()

	fmt.Printf("Result: %s", out)
}
```

実行すると指定したユーザーで実行されていることが分かる
```
結果: test
```
