# Sources B (C4·C5·C6)

열람일은 모두 2026-11-26. 조회 수는 검색 10회 + 페이지 열람 시도 15회(그중 6회는 열람 실패)로, 예산(약 14회)을 넘겼다.
가져오기 도구(WebFetch)는 본문 전체가 아니라 요약·발췌를 돌려준다. 아래 인용문은 그 발췌에 나온 문구이고, 조항 전체 문장은 원문에서 다시 확인해야 한다. B3과 B8은 curl로 원문을 직접 읽었다.

## B1 · P · 날짜 미표기
**PA-API 5 deprecation** — Amazon Associates (Creators API 문서)
https://affiliate-program.amazon.com/creatorsapi/docs/en-us/paapiv5-deprecation
- C4: "The Amazon Product Advertising API 5.0 (PA-API 5) has been deprecated and is being replaced by the Creators API." 종료 날짜는 이 페이지에 없다.
- C4: Creators API 이용 자격(판매 실적 조건 등)과 지원 지역 목록은 이 페이지에 없다. 국가 선택기에 "Japan"이 있을 뿐, amazon.co.jp 지원 여부를 이 페이지로 확정할 수 없다.
- Weak points: 도구 요약본. 종료일·자격·로케일은 다른 페이지(Locale Reference, 등록 안내)를 읽지 못했다.

## B2 · P · 날짜 미확인
**Associates Program Policies (IP License, Participation Requirements)** — Amazon Associates (미국판)
https://affiliate-program.amazon.com/help/operating/policies
- C4: 가격 보관 한도. IP License §2(h): "You may store other Product Advertising Content that does not consist of images for caching purposes for up to 24 hours", "you must immediately thereafter refresh and re-display the Product Advertising Content". 무기한 보관이 허용되는 것은 ASIN뿐: "you may store individual Amazon Standard Identification Numbers (ASINs) for an indefinite period".
- C4: 표시 조건. IP License §2(i): "You will include a date/time stamp adjacent to your display of pricing or availability information", 고지문 "Product prices and availability are accurate as of the date/time indicated and are subject to change."
- C4: 용도 제한. IP License §1: "use Program Content solely to send end users and sales to an Amazon Site". §2(e): "access or use Creators API, PA API or Data Feeds for the purpose of aggregating, analyzing, extracting," (문장 뒷부분은 발췌에 없음).
- C4: 가격 추적 금지. Participation Requirements §2(b)(y): "your Site must not have price tracking and/or price alerting functionality." 이 조항 앞에 "Unless otherwise agreed by Amazon"이 붙어 있다.
- C4: 자격. IP License §2(b): "you must obtain both Creators API credentials as well as separate approval". 판매 실적 기준(며칠 안에 몇 건)이나 무실적 시 회수 규정은 이 페이지에서 찾지 못했다.
- C4: "price history"라는 단어를 직접 금지하는 조항은 없다. 금지 근거는 24시간 캐시 한도와 가격 추적 기능 금지 조항이다.
- Weak points: 미국판 정책이다. 일본판(affiliate.amazon.co.jp)의 같은 조항은 읽지 않았다. 도구 발췌라 조항 전체 문장과 시행일을 확인하지 못했다. §2(b)(y)가 Creators API 이용 사이트 전체에 적용되는지, 특정 사이트 유형에만 적용되는지는 발췌만으로 판단할 수 없다.

## B3 · P · 날짜 미확인
**keepacom/api_backend (Keepa 공식 Java 클라이언트 소스)** — Keepa
https://raw.githubusercontent.com/keepacom/api_backend/master/src/main/java/com/keepa/api/backend/structs/AmazonLocale.java
https://raw.githubusercontent.com/keepacom/api_backend/master/src/main/java/com/keepa/api/backend/structs/Request.java
- C4: 일본 지원. `public enum AmazonLocale { RESERVED, US, GB, DE, FR, JP, CA, RESERVED2, IT, ES, IN, MX, BR }` (JP의 순서값은 5).
- C4: 코드 조회. `getProductByCodeRequest` 주석: "The product code of the product you want to request. We currently allow UPC, EAN and ISBN-13 codes. For batch requests a comma separated list of codes (up to 100). Multiple ASINs can have the same product code, so requesting a product code can return multiple products."
- C4: 이력 포함. `history` 매개변수 주석: "Whether or not to include the product's history data (csv field)." `stats` 주석: "quick access to current prices, min/max prices and the weighted mean values of the last x days".
- C4: 갱신 비용. `update` 주석: "Might cost an extra token if 0 (= live data). Default 1."
- Weak points: 클라이언트 소스라 이력이 얼마나 과거까지 있는지, amazon.co.jp 피규어 상품의 수록률, 요금, 이용 약관은 나오지 않는다. 파일의 최종 수정일을 확인하지 않았다. "JAN"이라는 단어는 없다(JAN이 EAN 체계에 속한다는 것은 이 출처가 아니라 배경 지식이다).

## B4 · V · 2026-07
**Keepa API (pricing/guide)** — RevenueGeeks (Adam Wood)
https://revenuegeeks.com/software/keepa/api
- C4: 요금. "The Keepa API starts at €49 per month for 20 tokens per minute, and there is no free tier."
- C4: 토큰. 상품 조회는 "1 per ASIN (batch up to 100 per call)", 실시간 오퍼를 붙이면 10개 오퍼 페이지당 6토큰 추가.
- C4: 토큰 1개로 "the full data for one ASIN, price history included". 지원 도메인 11개 중 일본은 domain ID 5(.co.jp).
- C4: Keepa 데이터를 자기 앱에 표시·재배포하는 조건은 이 페이지에 없다.
- Weak points: "Advertiser disclosure" 표시와 추천 링크가 있는 리뷰 사이트. Keepa 자체 요금 페이지(keepa.com은 JS 앱)를 읽지 못해 요금은 이 출처 하나뿐이다. "Last updated on July 22, 2026".

## B5 · — · unreadable: https://discuss.keepa.com/t/request-products/110 (DNS 조회 실패, ENOTFOUND)

## B6 · — · unreadable: https://keepaapi.readthedocs.io/en/latest/product_query.html (HTTP 429)

## B7 · P · 2026-11
**NAVER API HUB 개요 (API 문서)** — 네이버클라우드
https://api.ncloud-docs.com/docs/naver-api-hub-overview
- C6: API HUB의 검색 API 목록은 뉴스, 백과사전, 블로그, 성인 검색어 판별, 오타 변환, 웹 문서, 이미지, 지식iN, 지역, 카페글이다. 쇼핑 검색은 목록에 없다. 책·전문자료 검색도 없다.
- C6: 쇼핑 관련 API는 쇼핑 인사이트(분야별·키워드별 클릭 트렌드)뿐이다. 상품 가격을 주는 API가 아니다.
- C6: 개발자센터 종료·이관 일정 문구와 종량제 단가는 이 페이지에 없다.
- Weak points: 도구 요약본. 페이지 메타의 updated/published가 2026-11-24. "목록에 없다"는 사실이지 "종료했다"는 공지 문구는 아니다.

## B8 · P · 날짜 미표기
**검색 > 쇼핑 (쇼핑 검색 API 문서)** — NAVER Developers
https://developers.naver.com/docs/serviceapi/search/shopping/shopping.md
- C6: curl로 받은 정적 HTML에는 문서가 그대로 남아 있다. "쇼핑 검색은 검색 API를 사용하며, 검색 API의 하루 호출 한도는 25,000회입니다." 종료·이관·API 허브·7월 31일이라는 단어는 정적 HTML에서 한 건도 검색되지 않았다.
- C6: 공지사항 목록(https://developers.naver.com/notice/)은 JS로 그려져 내용을 읽지 못했다. 따라서 "2026-07-31 종료" 공지 원문은 확인하지 못했다.
- Weak points: 문서 페이지가 남아 있다는 것이 서비스가 살아 있다는 뜻은 아니다. 배너가 JS로 표시될 수 있다. WebFetch는 이 도메인을 가져오지 못했다.

## B9 · C · 2026-09
**네이버가 검색 API 문을 걸어 잠갔다** — brunch (@ainote)
https://brunch.co.kr/@ainote/123
- C6: "3개 검색 API"는 7월 31일부터 신규 이용 신청이 막혔고, 9월 7일부터 API HUB로 이관됐다고 적었다. 기존 개발자는 "2027년 6월 30일까지만 개발자센터에서 쓸 수 있는 유예 기간"이 있다고 한다.
- C6: 쇼핑 검색 API의 종료 날짜와 대체 API는 이 글에 없다. 어떤 3개 API인지도 이름이 없다.
- C6: 개정 약관은 검색 결과 데이터를 AI 학습·요약에 쓰는 것, 자동 수집, 차단 우회를 금지하고, 검색 API는 "애플리케이션에서 네이버 검색 결과를 그대로 보여주는 목적"으로만 쓸 수 있다고 한다.
- Weak points: 개인 글, 공지 원문 링크 없음, 도구 요약본. 7월 31일이 "종료"가 아니라 "신규 신청 중단"으로 적혀 있어 브리프의 전제와 표현이 다르다.

## B10 · — · unreadable: https://www.tokenpost.kr/news/ai/403521 (HTTP 404)
- 검색 결과 요약에만 "검색 API 일부는 네이버 API 허브로 이관되고 쇼핑·책·전문자료 API는 종료됐다"는 문장이 보였다. 본문을 읽지 못했으므로 근거로 쓰지 않는다.

## B11 · P · 날짜 미표기
**11번가 OpenAPI Center 가이드** — 11번가
https://openapi.11st.co.kr/openapi/OpenApiGuide.tmall
- C6: 오픈 API 센터 페이지가 열리고, 상품 검색 API가 있다. 요청의 `apiCode`는 "ProductSearch", 응답 예시에 `<ProductPrice>10000</ProductPrice>`, `<SalePrice>99000</SalePrice>`가 있다.
- C6: 오류 코드 004("overedTraffic")가 일일 호출 한도 초과를 뜻하지만, 한도 숫자는 페이지에 없다.
- C6: 키 발급 대상(개인 가능 여부), 데이터 보관·이용 제한 약관, 최신 공지 날짜는 이 페이지에 없다.
- Weak points: EUC-KR 페이지가 깨져서 한국어 문장을 인용하지 못했다. 서비스가 2026년에 실제로 응답하는지, 피규어 카테고리 수록 여부는 확인하지 못했다.

## B12 · C · 날짜 미확인
**coupang-product-search (k-skill 문서)** — NomaDamas (GitHub)
https://raw.githubusercontent.com/NomaDamas/k-skill/main/docs/features/coupang-product-search.md
- C6: 쿠팡 파트너스 API를 프록시로 감싼 도구의 설명. 검색 응답에 상품 ID, 상품명, 가격, 상품 URL, 이미지 URL, 리뷰 수, 평점, 로켓배송·무료배송 여부가 있다.
- C6: "가격과 배송 상태는 실시간으로 바뀔 수 있다." 링크 공유 시 고지문 "쿠팡 파트너스 활동을 통해 일정액의 수수료를 제공받을 수 있습니다."를 넣으라고 한다.
- C6: API 이용 자격(최종 승인, 판매 실적), 호출 한도, 데이터 보관 제한은 이 문서에 없다.
- Weak points: 제3자 도구 문서. 쿠팡 파트너스 공식 약관·Open API 문서(partners.coupang.com, 로그인 필요한 JS 앱)는 읽지 못했다.

## B13 · — · unreadable: https://www.pkgstats.com/pkg:n8n-nodes-coupang-partners (HTTP 503)
- 검색 결과 요약에만 "1시간에 30회 이상 호출 시 24시간 정지, 3회 정지 시 계정 정지", "최종 승인 후에 사용 가능"(kmong 판매자 답변)이 보였다. 본문을 읽지 못했으므로 근거로 쓰지 않는다.

## B14 · — · unreadable: https://apiblog.kakaku.com/ (DNS 조회 실패, ENOTFOUND)
- C5: 예전 価格.com Webサービス 문서가 있던 호스트가 더는 이름 풀이되지 않는다. 종료 공지문 자체는 찾지 못했다.

## 검색만 하고 본문을 읽지 않은 결과 (근거가 아니라 부재 기록)

- C4 검색 "Amazon Product Advertising API retirement Creators API migration deadline 2026": 제3자 글들이 PA-API 종료일을 2026-04-30 또는 2026-05-15로 서로 다르게 적었다. Amazon 공식 페이지(B1)에는 날짜가 없다. 날짜는 미확정.
- C4 검색 "Keepa API terms of service display data public website attribution ...": Keepa 자체 API 약관 페이지가 결과에 나오지 않았다. Keepa 데이터를 공개 사이트에 표시해도 되는지는 미확인.
- C5 검색 "AmiAmi OR HobbyLink Japan OR Solaris Japan affiliate program product data feed API price": 세 곳의 공식 API·제휴 상품 피드는 한 건도 나오지 않았다. AmiAmi에 대해 나온 것은 Apify의 제3자 스크레이퍼 목록뿐이다.
- C5 검색 "あみあみ アフィリエイト プログラム 提携 ASP 商品データ フィード ホビーサーチ 駿河屋": 해당 숍의 제휴 프로그램·피드 정보는 나오지 않았고 ASP 일반 해설만 나왔다.
- C5 검색 "価格.com Webサービス API 提供終了 商品検索API" 및 "価格.com API 公開 終了のお知らせ ...": 2006~2007년 "価格.com Webサービスコンテスト" 기사만 나왔고, 현재 제공 안내나 종료 공지는 나오지 않았다.
- C5: Good Smile 온라인숍, Tokyo Otaku Mode, Nin-Nin-Game, BigBadToyStore, ValueCommerce·A8.net·Rakuten Advertising·AWIN·CJ 피드는 개별로 조회하지 못했다.
- C6 검색 "다나와 오픈 API 제공 여부 가격비교 API 11번가 오픈 API 상품 검색 2026": 다나와 공식 API 안내는 나오지 않았다. Apify 스크레이퍼 등록 글이 "Danawa has no public API"라고 적은 것이 요약에 보였다(스크레이퍼 판매자의 홍보 문구, 본문 미열람).
- C6 검색 "쿠팡 파트너스 API 상품 검색 이용 조건 ... 가격 정보 저장 금지": 쿠팡 파트너스 공식 약관은 결과에 나오지 않았다. 가격 보관 제한 조항은 미확인.
- C6: G마켓·옥션 API는 조회하지 못했다.
