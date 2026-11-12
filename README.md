# Jelly Cloud

Jelly Cloud의 공개 CI·릴리즈 실행 리포다. 애플리케이션 소스와 요청 권한은 비공개 Core가 소유한다.

Core Bridge 요청을 gate와 worker에서 검증하고 정확한 소스를 체크아웃한다. 조회 토큰은 소스 실행 전에 폐기하며 원시 빌드 출력은 공개하지 않는다.

릴리즈는 Core가 승인된 소스 태그·CI·Release notes로 요청한다. Public은 native amd64·arm64 빌드와 smoke test, 이미지·의존성 검사를 수행하고 기존 비공개 GHCR 패키지에 발행한다. Public Release에는 승인된 노트와 image-digests.json을 게시하며 Core가 결과를 대조해 완료 기록을 남긴다.

Reader 키는 main 전용 core-read 환경에 저장한다. 같은 기존 App을 재사용하며 새 자격 증명을 발급하지 않는다.

CI·릴리즈는 [NoteHub](https://github.com/cagojeiger/notehub)와 같은 제어 패턴을 사용하며 [GPL-3.0](LICENSE)으로 제공한다.
