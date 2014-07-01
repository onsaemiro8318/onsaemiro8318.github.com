---
layout: post
title: "Ruby 설치"
description: ""
category: test
tags: [test, first]
---
{% include JB/setup %}

#### Ruby를 설치하기 전에
google에서 'os x rbenv' 검색하여 최신글 참고


#####1. Mac version 확인

#####2. Install command-line tools
터미널 실행  
~~~
git
~~~
설치를 묻는 창이 나타나면 install 클릭  

#####3. Install homebrew
~~~
ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
~~~
설치가 끝난 후
~~~
brew install git
~~~
git 설치가 끝난 후 Homebrew 업데이트
~~~
brew update
~~~
#####4. Install rbenv
~~~
curl -L https://raw.githubusercontent.com/fesplugas/rbenv-installer/master/bin/rbenv-installer | bash
~~~
설치가 완료되면
~~~
vi ~/.bash_profile
~~~
~/.bash_profile 안에 아래 내용을 입력한다.
~~~
export RBENV_ROOT="$HOME/.rbenv"

if [ -d $RBENV_ROOT ]; then
  export PATH="$RBENV_ROOT/bin:$PATH"
  eval "$(rbenv init -)"
fi
~~~
ESC키를 통해 빠져나온 후 ruvy, rbenv, brew, git 등 version 확인

#####5. Install MySQL
~~~
brew install mysql
~~~
~~~
gem install rails
~~~
~~~
brew services start mysq
~~~
~~~
brew install git
~~~
