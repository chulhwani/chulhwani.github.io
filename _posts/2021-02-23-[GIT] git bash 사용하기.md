<strong>1. GIT 다운로드(윈도우) 및 설치</strong>
<pre class="highlight"><code>https://git-scm.com/
</code></pre>
<p>&nbsp;</p>
<strong>2. GIT Config</strong>
<div class="language-plaintext highlighter-rouge">
<div class="highlight">
<pre class="highlight"><code><b># GIT 초기화(프로젝트 버전 관리 시작)</b>
cshim@CSHIM-KR MINGW64 /d/DOWNLOADs/GIT
$ git init
Initialized empty Git repository in D:/DOWNLOADs/GIT/.git/

cshim@CSHIM-KR MINGW64 /d/DOWNLOADs/GIT (master)
$ git config --global user.name "chulhwani"

cshim@CSHIM-KR MINGW64 /d/DOWNLOADs/GIT (master)
$ git config --global user.email "chulhwani@gmail.com"

cshim@CSHIM-KR MINGW64 /d/DOWNLOADs/GIT (master)
$ git config --list
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=false
credential.helper=manager-core
pull.rebase=false
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master
user.name=chulhwani
user.email=chulhwani@gmail.com
core.editor=code
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
difftool.sourcetree.cmd='' "$LOCAL" "$REMOTE"
mergetool.sourcetree.cmd=''
mergetool.sourcetree.trustexitcode=true
core.repositoryformatversion=0
core.filemode=false
core.bare=false
core.logallrefupdates=true
core.symlinks=false
core.ignorecase=true

cshim@CSHIM-KR MINGW64 /d/DOWNLOADs/GIT (master)
$ git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)

<b># Visual Studio Code 호출</b>
cshim@CSHIM-KR MINGW64 /d/DOWNLOADs/GIT (master)
$ code .
</code></pre>
</div>
</div>
<p>&nbsp;</p>
<strong>3. GIT 사용하기</strong>
<div class="language-plaintext highlighter-rouge">
<div class="highlight">
<pre class="highlight"><code>touch README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/akkias/HTML-Basics.git
git push -u origin mastertouch README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/akkias/HTML-Basics.git
git push -u origin mastertouch README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/akkias/HTML-Basics.git
git push -u origin mastertouch README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/akkias/HTML-Basics.git
git push -u origin master
</code></pre>
</div>
</div>
<p>&nbsp;</p>
