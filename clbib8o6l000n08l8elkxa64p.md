# Apptainer  とはなんぞやの紹介記事

最近知ったので存在を知って面白いなと思ったので雑記

[https://apptainer.org/](https://apptainer.org/)

大雑把な特徴として以下

*   root 権限を持つ Daemon プロセスが不要
    
*   Docker/OCI との100 % 互換性
    
    *   共有システム、特に HPC 環境での使用に適したランタイムの制約内で、Docker との最大の互換性を目指している・・・らしい
        
*   コンテナ形式が単一ファイル
    
*   デフォルトでrootlessコンテナが実行可能
    
*   GPUサポート
    

公式ではLinuxしかサポートしていないがMacでもlimaをインストールすると`apptainer.lima` でapptainerが動く環境が付いてくるので便利

ベアメタル/Docker/LXCと性能比較した\[論文\]([https://arxiv.org/abs/1709.10140](https://arxiv.org/abs/1709.10140))もあるので参考にどうぞ