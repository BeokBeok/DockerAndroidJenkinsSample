# DockerAndroidJenkinsSample
Docker와 Jenkins를 활용한 안드로이드 빌드 환경 구축 샘플
## 주의사항
1. M1인 경우, Docker의 환경을 `linux/amd64`로 해주어야 함
    - M1에서는 안드로이드 emulator를 지원하지 않아, build-tool이 설치되지 않음
    - Docker 빌드 시 `--platform linux/amd64` 옵션 적용
2. Jenkins LTS 버전 설치 권장 - [Jenkins LTS Changelog](https://www.jenkins.io/changelog-stable/)
    - Jenkins 버전이 낮으면, 플러그인이 제대로 설치되지 않아 일부 기능이 동작하지 않음
3. Java 11 버전 설치 권장
    - 11 버전이 설치되어 있지 않으면, Jenkins가 실행 되지 않음
4. 안드로이드 프로젝트에 맞는 gradle과 sdk 버전 설치 권장
    - 프로젝트 빌드가 실패함
5. Docker CLI 실행 시 루트 권한 적용 권장
    - `-u 0` 옵션 적용 (UID가 0이면 루트)
## 느낀점
- Docker 무료 버전으로는, 안드로이드 프로젝트 빌드 중 무한로딩 현상이 자주 발생하여 한계를 느낌
    - 매우 느린 환경 (심지어 CPU, 메모리, 디스크 용량 등 모두 MAX로 설정했는데도 느림)
    - 기도 메타로 빌드가 성공하길 기대해야함
