---
title: 'Svelte Seoul 블로그에 기여하기'
summary: '누구나 블로그에 글을 쓸 수 있고, 블로그 자체를 수정할 수도 있습니다.'
date: '2021-10-22'
author: 이유종(https://github.com/yujong-lee)
tag: '공지'
toc: true
---
처음에는 어려울 수 있지만 익숙해지면 간단합니다. 어려움이 있으시면 [Slack](https://join.slack.com/t/svelteseoul/shared_invite/zt-xf8buzpe-xZnJcIWJFHj9fueYZojPNw)에 오셔서 편하게 말씀해주세요.

## 작업 환경 준비하기

먼저 `Svelte-Seoul/svelte-seoul.github.io` 저장소를 Fork하고 Fork된 저장소를 `git clone`으로 자신의 컴퓨터로 복사합니다. 이후 `yarn` 으로 필요 패키지들를 설치합니다.

```bat
git clone git@github.com:[자신의 아이디]/svelte-seoul.github.io.git
cd svelte-seoul.github.io
yarn
```

이때 Fork한 자신의 저장소는 `origin`으로 등록되어 있습니다.  `upstream`도 추가해줍니다.

```bat
git remote add upstream git@github.com:Svelte-Seoul/svelte-seoul.github.io.git
```

`origin`과 `upstream`이 잘 등록되어 있는지는  `git remote -v`로 확인할 수 있습니다.

`Pull Request`를 보내기 전에는 `master branch`로부터 `git fetch upstream`한 뒤, git rebase master 하여야 합니다. 현 상태를 확인을 위해서는 `git log --decorate --oneline --all --graph` 명령어, 또는 `SourceTree`같은 도구가 유용할 수 있습니다.

`git`이 익숙하지 않으시다면 [git-scm](https://git-scm.com/book/ko/v2)을 참고하면서 `svelte-seoul.github.io`에 기여하면서 연습해보시는 것이 가장 좋습니다. 여기서는 실수하면서 천천히 연습하셔도 상관없습니다.

## 로컬에서 블로그 실행하기

```bat
yarn start
```

위 명령어를 입력하면 `localhost`에서 블로그가 실행됩니다. 포트번호는 기본 3000입니다. 블로그에 뭔가 변화를 가하고, 새로고침하면 바로 반영되니다. `Rollup`은 `Hot Reloading`을 지원하지 않으므로, 변화를 가하고 그것을 확인하려면 웹사이트를 새로고침해야 합니다.

## 작업 후 커밋하기

작업을 마친 뒤에는 반드시 `yarn build`를 실행한 뒤, 그것의 결과를 포함한 모든 변화들을 `commit`해서 그것들을 `origin`에 보내야합니다. 커밋은 하나로 뭉칠수도 있지만, 이왕이면 적당한 의미단위로 나누는 것이 좋습니다.

기본적인 가이드라인은 작업물과 build의 결과를 나누는 것입니다. 즉, `src` 폴더에 가해진 변화와 `docs`폴더에 가해진 변화를 `commit`에서 구분하는 것입니다.

커밋 메시지에 간결한 설명을 담아주시는게 가장 좋지만(`What`보다는 `Why`가 더 중요합니다), 어려우시면 `Pull Request`의 본문에 잘 정리해주셔도 괜찮습니다. `Pull Request`의 단위는 최대한 작게 유지해주시면 좋습니다.

## Pull Request 보내기

자신의 저장소(`origin, my-branch`)로부터 `Svelte-Seoul(upstream, master)`로 `Pull Request`를 보내시면 됩니다. 저장소의 `Pull Request` 탭에 들어가셔서 진행하시면 됩니다.

## 리뷰 반영하기

자신의 `Pull Request`에 대한 리뷰를 반영하거나, 뭔가 수정하고 싶다면 자신이 작업하던 `branch`에 그대로 `commit`을 `push`하면 됩니다. 그러면 `Pull Request`에 해당 커밋이 그대로 추가됩니다. 따라서 `Pull Request`가 `merge`되기 전까지 `fork`된 저장소나 `branch`를 삭제하면 안됩니다.

```bat
// my branch에 새로운 커밋 생성
git push origin [my branch]
```
