# Diana 컨셉 퀴즈 — Claude 작업 가이드

## 라이브 링크
https://studio-dia.github.io/diana01/Diana_ver0.4.html

## GitHub 레포
https://github.com/studio-dia/diana01
Remote: `https://studio-dia@github.com/studio-dia/diana01.git`

## 편집 대상 파일
`Diana_ver0.4.html` (이 폴더 안에 있는 파일이 실제 배포 파일)

소스 원본: `/Users/hwawonkim/Desktop/Dia_Diana_Dion/02_Diana/Diana_ver0.4.html`
→ 수정할 때는 두 파일 모두 동일하게 유지할 것

## 수정 후 배포 절차
파일 수정이 끝나면 반드시 아래 순서로 push:

```bash
cd /Users/hwawonkim/Desktop/Dia_Diana_Dion/diana01
git add Diana_ver0.4.html
git commit -m "수정 내용 요약"
git push
```

push 후 1~2분 내에 라이브 링크에 자동 반영됨 (GitHub Actions Pages 배포).

## 파일 구조
- 번들 형식: `__bundler/manifest` (base64+gzip JS) + `__bundler/template` (JSON HTML)
- JS UUID: `810bbe49-210b-45a3-81e2-da5ee3874628`
- JS 수정: decode(gzip+base64) → 문자열 치환 → encode → 파일에 덮어쓰기
- CSS/색상 수정: raw HTML에서 hex 코드 직접 치환 (절대 JSON parse/re-serialize 금지)

## 주요 설정값
- 컨셉 수: 22개 (미스테리가든 삭제됨)
- 우선순위: 로지 > 코지베드룸 > 매거진 > 폴라로이드3 > 젝시
- 코지베드룸: 이미지 4장 랜덤 로테이션
- 매거진: 이미지 5장 랜덤 로테이션
- 색상 테마: Blue Steel
- QUESTION_WEIGHTS: [3, 2, 3, 2, 0]

## 컨셉 그룹
- 웨이브: 웨이브, 퓨어웨이브, 딥웨이브, 블랙웨이브
- 시그니처: 글로우모닝, 코지베드룸, 스타라이트, 로제
- 호리존: 나머지 전부 (기본값)
