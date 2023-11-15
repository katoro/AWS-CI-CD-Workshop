# Github Repo 등록

* Cloud9 콘솔에 접속하여 아래 명령어를 실행하시면 기본 스켈레톤 React 프로젝트가 생성됩니다.

```
cd /home/ec2-user/environment
npx create-react-app aws-react-sample
```

<figure><img src=".gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

* 깃헙에 빈 리포지토리를 만들거&#x20;

<figure><img src=".gitbook/assets/스크린샷 2023-02-22 오후 2.53.23.png" alt=""><figcaption></figcaption></figure>

* 생성이 완료되면 아래와 같이 프로젝트를 등록하는 방법을 안내해줍니다.

<figure><img src=".gitbook/assets/스크린샷 2023-02-22 오후 2.53.47.png" alt=""><figcaption></figcaption></figure>

* 프로젝트 등록에 앞서서 Developer Setting 페이지로 이동합니다. 인증을 위한 임시 토큰을 만들기 위함입니다.

<figure><img src=".gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

* Persona lAccess Tokens을 만들어줍니다.

<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

* 아래와같이 토큰값이 생성됩니다.







```
cd /home/ec2-user/environment/aws-react-sample

git remote add origin https://github.com/{yourGithubId}/aws-react-sample.git
git branch -M main
git push -u origin main
```

user/ password 기입





