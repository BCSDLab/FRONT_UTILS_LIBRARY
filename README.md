# BCSDLab 프론트엔드 패키지

BCSDLab 프론트엔드 프로젝트가 함께 쓰는 npm 패키지 모음입니다.

| 패키지 | 설명 |
| --- | --- |
| [`@bcsdlab/utils`](packages/utils) | 공통 유틸 (`cn`, `sha256`, `josa`) |
| [`@bcsdlab/koin`](packages/koin) | 코인 서비스 유틸 (`isKoinError`, `sendClientError`) |

## 개발

```bash
corepack enable
pnpm install
pnpm build
```

## 배포

1. 패키지를 수정한 PR에 `pnpm changeset`으로 변경 내용을 추가합니다.
2. PR이 `main`에 머지되면 GitHub Actions가 **패키지 버전 반영** PR을 만듭니다.
3. 그 PR을 머지하면 바뀐 패키지가 npm에 배포되고 삐봇이 `#트랙_front_end`에 알립니다.

npm 배포는 trusted publishing(GitHub OIDC)으로 하므로 npm 토큰이 필요 없습니다. 새 패키지를 추가할 때는 npm `@bcsdlab` 조직 관리자가 패키지 설정에 이 저장소와 `release.yml`을 등록해야 합니다.
