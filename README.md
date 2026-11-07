# story-library

한 손으로 보는 뷰어용 소설·만화·이미지·음성 저장소입니다.
뷰어는 `library.json` 목록에 있는 **최신 버전만** 보여줍니다.

## 구조

```
library.json            목록 (뷰어가 읽는 파일)
novels/<이름>/v1/text.md          소설 본문 (삽화는 본문 안 ![...](illustrations/xxx.svg) 위치에)
novels/<이름>/v1/illustrations/   소설 삽화
novels/<이름>/v0/text.md          옛날 버전 (목록에 없어 뷰어에 안 보임)
comics/<이름>/v1/pages/page-N.svg 만화 페이지 (순서대로)
images/<이름>/v1/*.svg            이미지
audio/<이름>/v1/*.mp3             음성
```

## 새 글 등록하는 법

1. 종류 폴더 안에 `<이름>/v1/` 폴더를 만듭니다.
2. 파일을 넣습니다. (소설은 `text.md`, 만화는 `page-1.svg`부터, 음성은 `mp3`)
3. `library.json`의 `items`에 한 줄을 추가합니다. `version`은 `v1`로 적습니다.
4. 고칠 때는 `v1` 폴더를 통째로 복사해 `v2` 폴더를 만들고, `library.json`의 `version`만 `v2`로 바꿉니다. 옛날 버전은 지우지 않아도 뷰어에 안 보입니다.

## 지금 들어 있는 샘플

- 소설: 비 오는 날의 카페 (v1, 삽화 2장)
- 만화: 아침 고양이 (v1, 4쪽)
- 이미지: 저녁 하늘, 찻잔 (각 v1)
- 음성: 아침 읽기 (v1, 소설 첫 부분 낭독)
