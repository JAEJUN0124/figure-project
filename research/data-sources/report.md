# FigureVault가 문제 없이 데이터를 확보할 방법

2026-11-26 조사 · standard 깊이 (조회 72회, 예산 초과) · 출처 39건 기록, 그중 읽을 수 있었던 것 27건

## 답

**모든 문제가 깨끗하게 풀리는 단일 소스는 없다. 다만 서비스를 두 층으로 나누면 진행할 수 있다.**

1. 컬렉션 관리, 구매 기록, 지출 대시보드, 사용자가 직접 적는 가격은 외부 데이터가 필요 없어 약관 위험이 없다. 이 층만으로도 서비스가 성립한다.
2. 자동 가격 수집은 후보가 Yahoo! 쇼핑 API 하나로 좁혀진다. 보관을 금지하는 조항은 없지만 허용한다는 조항도 없고, 한국에서 키를 발급받을 수 있는지는 확인되지 않았다.

Amazon 공식 API는 가격 추적을 약관으로 금지하고, 라쿠텐은 가격 비교 구성과 충돌하는 조항이 있으며, MFC와 하비샵은 허용 근거를 찾지 못했다.

## 주장별 판정

| 주장 | 판정 | 근거 |
|---|---|---|
| C1 Yahoo! 약관이 가격 장기 보관을 허용한다 | mixed (금지·허용 조항 모두 없음) | [A1](#출처), [A2](#출처), [A3](#출처), [A5](#출처), [A6](#출처) |
| C2 라쿠텐 약관이 장기 보관을 허용하고 JAN 조회 API가 있다 | mixed (JAN 부분은 refuted 쪽) | [A8](#출처), [A10](#출처), [A11](#출처), [A12](#출처) |
| C3 한국 거주 개인이 두 서비스의 API 키를 발급받을 수 있다 | unknown | [A2](#출처), [A4](#출처), [A8](#출처), [A13](#출처) |
| C4 Amazon 또는 Keepa로 가격 이력을 합법적으로 얻어 표시할 수 있다 | mixed (Amazon refuted, Keepa 약관 미확인) | [B1](#출처), [B2](#출처), [B3](#출처), [B4](#출처) |
| C5 하비샵·가격비교 사이트에 쓸 수 있는 공식 API·피드가 있다 | unknown (refuted 쪽) | [B14](#출처) |
| C6 국내 공식 소스로 피규어 판매가를 조회·보관할 수 있다 | mixed | [B7](#출처), [B8](#출처), [B9](#출처), [B11](#출처), [B12](#출처) |
| C7 MFC가 카탈로그 데이터의 제3자 이용을 허용한다 | unknown (refuted 쪽) | [M1](#출처) |
| C8 구조화된 피규어 카탈로그를 자유 이용 조건으로 얻을 수 있다 | mixed (단일 소스로는 없음) | [M3](#출처), [M5](#출처), [M8](#출처), [M9](#출처), [M10](#출처), [M11](#출처), [M12](#출처) |

## 상세

### 가격 소스 비교

| 소스 | 장기 보관 | JAN 조회 | 비용 | 걸리는 점 | 결론 |
|---|---|---|---|---|---|
| Yahoo! 쇼핑 API | 금지·허용 조항 없음 | 있음 | 무료 | "제공 목적 초과 이용" 금지, 대가를 받는 이용 금지, 크레딧 표시 의무, 한국 발급 미확인 | 유일한 후보 |
| 라쿠텐 웹 서비스 | 기간 조항 없음, 공개 저장 금지 조항 있음 | 문서에 없음 | 무료 | 같은 화면에 라쿠텐 외 링크 금지, 경쟁 서비스 금지 | 보류 |
| Amazon 공식 API | 24시간까지 | 미확인 | 무료 (제휴 승인 필요) | 가격 추적·알림 기능 금지 | 탈락 |
| Keepa API | 미확인 | 있음 (EAN) | 월 €49부터 | 공개 표시 약관 미확인, 유료 | 보류 |
| 하비샵·価格.com | 해당 없음 | 해당 없음 | 해당 없음 | 공식 API·피드를 찾지 못함 | 탈락 |
| 11번가 Open API | 미확인 | 미확인 | 미확인 | 발급 조건·커버리지 미확인 | 추가 확인 대상 |
| 네이버 쇼핑 검색 | 해당 없음 | 해당 없음 | 해당 없음 | API HUB 목록에 없음 | 탈락 |

### Yahoo! 쇼핑 API (C1)

가이드라인, 공통 이용규약 전문, API 문서, 크레딧 페이지, FAQ를 원문으로 읽었으나 보존·캐시·축적·24시간을 다루는 조항이 없다 ([A1](#출처), [A2](#출처), [A3](#출처), [A5](#출처), [A6](#출처)). 다음 일반 조항이 범위를 정한다 ([A2](#출처)).

- 제1장 14: "当社サービスやそれらを構成するデータを、その提供目的を超えて利用することができません"
- 제2장 3(3): "対価を受ける目的でソフトウェアまたは開発ソフトウェアを自ら利用し、または第三者に利用させること" (금지)

가격 이력 축적이 "제공 목적 초과"인지는 조문에 정의가 없다. 대가 수취 금지 조항 때문에 유료 요금제나 수익화는 이 API와 함께 쓸 수 없다고 보는 것이 안전하다.

운영 조건은 확인됐다. 크레딧 표시는 의무다: "APIを利用するすべてのサイトやアプリケーションには、クレジットを表示する必要があります" ([A5](#출처)). 호출 한도는 초당 1회이고 ([A3](#출처)), FAQ에 Client ID당 1일 50,000회 상한이 나오지만 상품검색 v3에 그대로 적용되는지는 확정하지 못했다 ([A6](#출처)).

### 라쿠텐 웹 서비스 (C2)

일본어 원문은 사이트가 계속 503이라 읽지 못했고, 아카이브된 영문 참고 번역을 읽었다. 규약은 2012-06-28 개정 이후 바뀌지 않았다 ([A8](#출처), [A12](#출처)).

- 제10조 1항 9호: "Storing information obtained through the Web Services or the Applications in a place that enables the sharing of information with unspecified and/or many people" (금지)
- 제8조 4항: "the Developer must not provide links to websites other than the Rakuten Sites in the parts of the Applications where the Web Services has been used"

제8조 4항은 Yahoo! 가격과 라쿠텐 가격을 한 화면에 나란히 놓고 각 판매처로 링크하는 구성과 충돌한다. 제품 검색 API는 개편 후 목록에 남아 있으나 ([A10](#출처)), 문서상 입력이 keyword·genreId·productId뿐이고 JAN이 입출력 어디에도 없다 ([A11](#출처), 개편 전 캡처).

### Amazon과 Keepa (C4)

Amazon 제휴 정책(미국판)은 세 가지로 막는다 ([B2](#출처)).

- 보관: "You may store other Product Advertising Content that does not consist of images for caching purposes for up to 24 hours"
- 기능: "your Site must not have price tracking and/or price alerting functionality" (Amazon이 따로 동의한 경우 제외)
- PA-API 5는 폐기되어 Creators API로 대체 중이며 별도 승인이 필요하다 ([B1](#출처))

Keepa는 Amazon 가격 이력을 이미 쌓아 둔 제3자 서비스다. 공식 클라이언트 소스에서 일본 로캘, UPC·EAN 코드 조회, 이력 반환을 확인했다 ([B3](#출처)). 요금은 월 €49부터, 무료 등급 없음이라는 리뷰 사이트 근거뿐이다 ([B4](#출처)). 받은 데이터를 공개 서비스에 표시해도 되는지는 약관을 읽지 못했다.

### 국내 소스 (C6)

네이버 API HUB 공식 개요(2026-11-24)에 쇼핑 검색이 없고, 쇼핑 관련은 추세 데이터인 쇼핑 인사이트뿐이다 ([B7](#출처)). 종료일을 공식 공지로 확인하지는 못했다. 개인 글은 7월 31일부터 신규 신청이 막혔고 기존 개발자는 2027-06-30까지 유예라고 적었으나, 쇼핑 검색을 특정하지 않는다 ([B9](#출처)).

11번가 Open API 센터에는 가격 필드(`ProductPrice`, `SalePrice`)가 있는 `ProductSearch`가 있다 ([B11](#출처)). 키 발급 조건, 한도, 보관 약관, 피규어 커버리지는 모두 미확인이다. 쿠팡 파트너스는 제3자 문서로 응답 항목만 확인했다 ([B12](#출처)).

### 카탈로그 (C7, C8)

- **MFC**: 약관 페이지가 자동 조회에 403을 돌려준다 ([M1](#출처)). 공식 API, 내보내기, 제휴 안내를 찾지 못했다.
- **Wikidata**: 개별 피규어가 항목으로 없다. 일본 접두 GTIN을 가진 항목이 전체에서 445건이다 ([M3](#출처)).
- **제조사**: 굿스마일 공식 사이트에 피드·API가 없고 상품 목록에 JAN이 없다 ([M8](#출처)). 이용규약 제19조는 지식재산권이 회사에 귀속된다고만 정한다 ([M9](#출처)).
- **오픈 데이터셋**: Hugging Face `p1atdev/pvc`가 CC0 선언, 7,902건이며 JAN·작품·캐릭터·제조사 키가 있다 ([M10](#출처)). 제조사 사이트를 스크레이핑한 것이라 CC0는 올린 사람의 선언일 뿐이고, 2023년 발표분까지다.
- **작품·캐릭터 이름**: AniList는 비상업 무료이나 대량 수집·저장을 금지한다 ([M5](#출처), 도구 요약본). MyAnimeList API는 스크레이핑 금지와 상업 수익 제한이 있다 ([M11](#출처)).
- **사용자 기여 방식**: iCollect Everything은 바코드 스캔과 사용자 기여로 DB를 만든다고 밝힌다 ([M12](#출처), 자사 블로그). 일본 피규어 사례는 아니다.

## 제안 (판단)

아래는 증거가 강제하는 결론이 아니라, 판정 결과를 놓고 내린 판단이다.

| 안 | 내용 | 약관 위험 | 잃는 것 |
|---|---|---|---|
| 1. 두 층 구성 (권장) | 핵심은 외부 데이터 없이 만들고, 자동 가격은 Yahoo! 하나만 붙인다 | 핵심 층은 없음, 가격 층은 해석 여지 | 쇼핑몰별 비교, 수익화 |
| 2. 수동 기록만 | 가격도 사용자가 직접 적는다 | 없음 | 자동 갱신 |
| 3. Keepa 유료 | Amazon 일본의 과거 이력까지 받는다 | 표시 약관 미확인 | 월 €49 이상 |
| 4. 국내 가격 추가 | 11번가 Open API로 원화 가격을 붙인다 | 미확인 | 확인 전에는 판단 불가 |

안 1을 권한다. 이유는 세 가지다.

- 핵심 층이 외부 소스와 무관해, Yahoo! 쪽 확인이 어떻게 나오든 프로젝트가 멈추지 않는다.
- 카탈로그는 사용자가 JAN으로 등록할 때 Yahoo! 응답으로 상품명과 이미지를 채우고, 작품·캐릭터는 사용자가 입력한다. 중앙 카탈로그 소스가 없다는 C8 결과와 맞는다.
- 가격 층이 막히면 안 2로 내려가면 되고, 코드 구조(소스 어댑터)는 그대로다.

README에서 바꿔야 할 점도 생겼다. 라쿠텐은 "채택"에서 "보류"로 내려야 하고, 네이버 종료일(2026-07-31)은 공식 근거가 없어 표현을 낮춰야 하며, 서비스가 무료·비영리라는 전제를 명시해야 한다.

## 주의

- 약관 인용 중 Amazon은 미국판 정책이고 발췌 단위로 읽었다. 일본판은 확인하지 않았다.
- 라쿠텐 규약은 법적 효력이 없다고 스스로 밝힌 영문 참고 번역이다.
- Keepa 요금은 광고 수익이 있는 리뷰 사이트 근거뿐이다.
- "찾지 못했다"는 판정(C5, C7)은 부재의 증명이 아니다. 조사하지 못한 곳이 남아 있다.
- 약관에 금지 조항이 없다는 것과 운영사가 실제로 문제 삼지 않는다는 것은 별개다.

## 남은 확인

| 순서 | 확인할 것 | 방법 | 결과에 따라 |
|---|---|---|---|
| 1 | 한국에서 Yahoo! JAPAN ID 가입과 앱 등록이 되는가 | 직접 가입 시도 (약 10분) | 안 되면 안 2 또는 안 4로 전환 |
| 2 | 가격 이력 축적이 Yahoo! API의 제공 목적 범위인가 | 개발자 문의, "WebAPIの商用利用について" 문서를 브라우저로 열람 | 불가 답변이면 안 2 |
| 3 | JAN 조회 결과가 쓸 만한가 | 실제 상품 30~50건 조회 | 필터 규칙 확정 |
| 4 | 11번가 Open API의 발급 조건, 보관 약관, 피규어 커버리지 | 가입 후 약관과 응답 확인 | 되면 국내 가격 층 추가 |
| 5 | MFC 약관과 내보내기 기능 | 로그인한 브라우저로 직접 열람 | 내보내기가 있으면 가져오기 기능 검토 |
| 6 | 라쿠텐 일본어 원문 규약 | 사이트 복구 후 열람 | 제8조 4항 해석 확정 |

## 출처

- **A1** · P · 2023-10 · [Yahoo!デベロッパーネットワーク ガイドライン — LINEヤフー](https://developer.yahoo.co.jp/guideline/)
- **A2** · P · 2023-10 · [LINEヤフー共通利用規約 — LINEヤフー](https://www.lycorp.co.jp/ja/company/terms/)
- **A3** · P · 2026-11 · [Yahoo!ショッピングAPI トップ — Yahoo!デベロッパーネットワーク](https://developer.yahoo.co.jp/webapi/shopping/)
- **A4** · P · 날짜 없음 · [利用制限について — Yahoo!デベロッパーネットワーク](https://developer.yahoo.co.jp/appendix/rate.html)
- **A5** · P · 날짜 없음 · [クレジット表示 — Yahoo!デベロッパーネットワーク](https://developer.yahoo.co.jp/attribution/)
- **A6** · P · 날짜 없음 · [Yahoo!ショッピングAPIのよくあるご質問 — Yahoo!デベロッパーネットワーク](https://developer.yahoo.co.jp/webapi/shopping/faq.html)
- **A8** · P · 2012-06 (2026-10-24 캡처) · [Rakuten Web Service: Terms of service, 영문 참고 번역 — Rakuten Group](https://web.archive.org/web/20261024225638/https://webservice.rakuten.co.jp/guide/rule)
- **A10** · P · 2026-10 (캡처) · [Rakuten Web Service: API 목록 — Rakuten Group](https://web.archive.org/web/20261005130824/https://webservice.rakuten.co.jp/documentation)
- **A11** · P · 2017-04 (2025-12-03 캡처) · [商品価格ナビ製品検索API — Rakuten Group](https://web.archive.org/web/20251203083021/https://webservice.rakuten.co.jp/documentation/ichiba-product-search)
- **A12** · P · 2012-06 (2023-12-11 캡처) · [Rakuten Web Service: Terms of service, 개편 전 캡처 — Rakuten](https://web.archive.org/web/20231211122911/https://webservice.rakuten.co.jp/guide/rule)
- **A13** · C · 2021-04 · [YahooJP ID with Japanese phone number — WaniKani Community](https://community.wanikani.com/t/yahoojp-id-with-japanese-phone-number/51068)
- **B1** · P · 날짜 없음 · [PA-API 5 deprecation — Amazon Associates](https://affiliate-program.amazon.com/creatorsapi/docs/en-us/paapiv5-deprecation)
- **B2** · P · 날짜 미확인 · [Associates Program Policies — Amazon Associates (미국판)](https://affiliate-program.amazon.com/help/operating/policies)
- **B3** · P · 날짜 미확인 · [keepacom/api_backend, 공식 Java 클라이언트 소스 — Keepa](https://raw.githubusercontent.com/keepacom/api_backend/master/src/main/java/com/keepa/api/backend/structs/AmazonLocale.java)
- **B4** · V · 2026-07 · [Keepa API pricing/guide — RevenueGeeks](https://revenuegeeks.com/software/keepa/api)
- **B7** · P · 2026-11 · [NAVER API HUB 개요 — 네이버클라우드](https://api.ncloud-docs.com/docs/naver-api-hub-overview)
- **B8** · P · 날짜 없음 · [검색 > 쇼핑 API 문서 — NAVER Developers](https://developers.naver.com/docs/serviceapi/search/shopping/shopping.md)
- **B9** · C · 2026-09 · [네이버가 검색 API 문을 걸어 잠갔다 — brunch](https://brunch.co.kr/@ainote/123)
- **B11** · P · 날짜 없음 · [11번가 OpenAPI Center 가이드 — 11번가](https://openapi.11st.co.kr/openapi/OpenApiGuide.tmall)
- **B12** · C · 날짜 미확인 · [coupang-product-search 문서 — NomaDamas (GitHub)](https://raw.githubusercontent.com/NomaDamas/k-skill/main/docs/features/coupang-product-search.md)
- **B14** · — · 읽을 수 없음 (DNS 실패) · [apiblog.kakaku.com](https://apiblog.kakaku.com/)
- **M1** · — · 읽을 수 없음 (HTTP 403) · [MyFigureCollection 약관](https://myfigurecollection.net/about/terms/)
- **M3** · P · 2026-11-26 · [Wikidata Query Service 직접 질의 — Wikimedia Foundation](https://query.wikidata.org/sparql)
- **M5** · P · 날짜 없음 · [Terms of Use, AniList APIv2 Docs — AniList](https://anilist.gitbook.io/anilist-apiv2-docs/docs/guide/terms-of-use)
- **M8** · P · 2026-11-26 열람 · [グッドスマイルカンパニー公式サイト — Good Smile Company](https://www.goodsmile.com/ja)
- **M9** · P · 2026-11-26 열람 · [利用規約 — Good Smile Company](https://www.goodsmile.com/ja/terms-of-use/)
- **M10** · C · 2023 · [p1atdev/pvc 데이터셋 — Hugging Face](https://huggingface.co/datasets/p1atdev/pvc)
- **M11** · P · 2019-08 · [API License and Developer Agreement — MyAnimeList](https://myanimelist.net/static/apiagreement.html)
- **M12** · V · 2026-03 · [Best Apps for Tracking Your Action Figure Collection (2026) — iCollect Everything](https://www.icollecteverything.com/?p=1765)
