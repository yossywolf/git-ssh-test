git-ssh-test
============

SSH経由でGitHubに接続できるかなー

# 1. 参考文献

[SSH認証キーをBitbucket/GitHubに設定しよう！ [Mac簡単手順] - 酒と泪とRubyとRailsと](http://morizyun.github.io/blog/ssh-key-bitbucket-github/)


# 2. 変えたところ

.sshというディレクトリにgithubというディレクトリを作成して鍵を新たに作りました
```
$ cd ~/.ssh/
$ mkdir github
$ ssh-keygen -t rsa -C test@example.com
```

ssh-keygenで鍵の生成先を聞かれるのでちゃんと指定する
```
Enter file in which to save the key (~/.ssh/id_rsa): ~/.ssh/github/id_rsa
```

~/.ssh/config もね☆
```
Host bitbucket.org
  HostName bitbucket.org
  IdentityFile ~/.ssh/github/id_rsa
  User git

Host github
  HostName github.com
  IdentityFile ~/.ssh/github/id_rsa
  User git
```

BitBucketの登録はまた今度で



# 3. オチ

学校からSSHの接続ができないの忘れてました
