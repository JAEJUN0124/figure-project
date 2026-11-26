# Sources: FigureVault 데이터 확보 방안

그룹별 번호를 그대로 유지한다. A = 일본 공식 API(Yahoo!·라쿠텐), B = 대체 가격 소스, M = 카탈로그 메타데이터.


---

<!-- sources-A.md -->

# Sources A — Yahoo! 쇼핑 API · 라쿠텐 웹 서비스 (C1, C2, C3)

열람일: 2026-11-26. 조회 수: 22회(검색 8, 페이지 14). 예산(약 12회)을 넘겼다. 라쿠텐 사이트 503과 Yahoo 헬프(JS 전용) 때문에 우회 조회가 늘었다.
가져온 방법: 공식 페이지는 `curl`로 원문 HTML을 받아 텍스트로 읽었다(요약 아님). A14만 WebFetch 요약이다.

## A1 · P · 2023-10
**Yahoo!デベロッパーネットワーク ガイドライン** — LINEヤフー株式会社
https://developer.yahoo.co.jp/guideline/
- C1: 페이지 전문이 짧고 보존·캐시·축적(保存, 蓄積, キャッシュ, 24時間, データベース) 관련 문구가 **없다**. 적용 규약을 이렇게 지정한다: "LINEヤフー共通利用規約（第2章 ソフトウェアに関する規則（ガイドライン）を含みます。）および プライバシーポリシー に加えて、このYahoo!デベロッパーネットワーク ガイドラインが適用されます。"
- C1: 특약은 두 가지뿐이다. "お客様が、当社が提供するAPIを使用してソフトウェアを開発する場合には、「クレジット表示ガイドライン」と「クレジット配置ルール」を順守しなければなりません。" / "お客様は、開発ソフトウェアに、当社が定める開発ソフトウェアを特定するためのアプリケーションID等を付さなければなりません。"
- 표기: "（2023年10月1日制定）"
- Weak points: none noted

## A2 · P · 2023-10
**LINEヤフー共通利用規約** — LINEヤフー株式会社
https://www.lycorp.co.jp/ja/company/terms/
- C1: 전문(제1장~제4장)에 API 데이터의 보존 기간·캐시·DB화에 관한 조항이 **없다** (찾아본 낱말: 保存, 蓄積, キャッシュ, 24時間 — "蓄積"은 제1장 15(8) 제3자 개인정보 수집 금지에만 나온다).
- C1: 데이터 이용 범위를 정하는 일반 조항. 제1장 14 "当社サービス等の再利用の禁止 お客様は、別途当社が定める場合を除き、当社サービスやそれらを構成するデータを、その提供目的を超えて利用することができません。" / 제1장 8.3 "お客様は、本コンテンツを、当社サービスが予定している利用態様を超えて利用（複製、送信、転載、改変を含みます。）をしてはなりません。"
- C1: 제2장(ソフトウェアに関する規則) 3 금지 행위. "（3）対価を受ける目的でソフトウェアまたは開発ソフトウェアを自ら利用し、または第三者に利用させること" / "（5）合理的に必要相当な数を超える利用、乱用等を行い、または、ソフトウェアの使用について当社が定める指示等を順守しない用法でソフトウェアを利用すること" / "（6）ソフトウェアを提供する目的に外れた態様でソフトウェアを利用したり、当社が不適当とみなした方法・態様でソフトウェアを利用したりすること"
- C1: 제2장 2 "ソフトウェアを介して当社サービスへのアクセス回数、アクセス時間等について制限すること等" 를 할 수 있다고 정한다.
- C3: 제1장 3.1 "当社は、当社サービスのご利用をアカウント（LINEアカウントやYahoo! JAPAN IDを含みます。）を登録された方に限定したり、…当社が定める本人確認等の手続を経て一定の要件を満たしたお客様のみに限定したりする等、利用に際して条件を付すことができるものとします。" 거주 국가 조건은 규약에 **없다**.
- C3: 제1장 17.1(4) "お客様が1年間以上アカウントまたは特定の当社サービスを使用していない場合" 계정·데이터 삭제 조치가 가능하다.
- 표기: 본문 끝에 "（2023年10月1日改定）", 이어서 "LINE利用規約 Yahoo! JAPAN利用規約 （2025年2月3日改定）"이 나온다. 뒤 날짜가 어느 문서의 것인지는 페이지 텍스트만으로 가리지 못했다.
- Weak points: 가격 이력 축적이 "提供目的を超えて"에 해당하는지는 조문에 정의가 없어 해석 문제로 남는다

## A3 · P · 2026-11
**ショッピング（Yahoo!ショッピングAPI トップ）** — Yahoo!デベロッパーネットワーク
https://developer.yahoo.co.jp/webapi/shopping/
- C1: 이용 방법 절의 주의 사항은 세 가지다. "Yahoo!ショッピングWeb APIをご利用いただくには、Yahoo!デベロッパーネットワーク ガイドラインへの同意が必要です。" / "…Yahoo!デベロッパーネットワークで登録したClient ID（アプリケーションID）を使用してください。" / "短い時間で同一URLに大量にアクセスを行った場合、一定時間利用できなくなることもあります。※（1クエリ/秒）". 보존·캐시 제한 문구는 **없다**.
- C1: 용도 설명 "デベロッパーがお持ちのコンテンツのリッチ化やアフィリエイトによるマネタイズにご活用いただけます。" (제휴는 "バリューコマース株式会社の提供するアフィリエイトプログラム")
- C1: 상품검색 설명 "キーワードでの商品検索をはじめ、JANコード、ジャンルカテゴリID、ブランドID、ストアIDでの商品検索を行い、JSON形式で各種商品情報を取得できます。"
- C1: "WebAPIの商用利用について" 링크가 헬프 사이트(A7)로 걸려 있다.
- 공지 최신 날짜: 2026.11.04
- Weak points: none noted

## A4 · P · 날짜 표기 없음
**利用制限について** — Yahoo!デベロッパーネットワーク
https://developer.yahoo.co.jp/appendix/rate.html
- C1: "制限を超えてリクエストを行った場合、エラーが返されます。詳細は各サービスごとの利用制限をご確認ください。" 이 페이지 자체에는 쇼핑 API의 수치가 없다.
- C3: "1つのYahoo! JAPAN IDにつき、アプリケーションは 10個 まで登録できます。" / "1年以上ご利用のないアプリケーションは削除させていただく場合があります。" 앱 등록 단위가 Yahoo! JAPAN ID임을 보여 준다.
- Weak points: 날짜 없음

## A5 · P · 날짜 표기 없음
**クレジット表示** — Yahoo!デベロッパーネットワーク
https://developer.yahoo.co.jp/attribution/
- C1: 표시 의무. "Yahoo!デベロッパーネットワークの提供するAPIを利用するすべてのサイトやアプリケーションには、クレジットを表示する必要があります。" / "クレジット表示は、Yahoo!デベロッパーネットワークの「APIドキュメント」ページにリンクしていなければなりません。"
- C1: 문구는 "Webサービス by Yahoo! JAPAN" 등 4종(A~D) 중 선택, HTML 변경 금지("CSSなどを利用してクレジットの表示色を変更したり、表示サイズを極端に小さくしたりすることも禁止します"), 위치는 "APIを利用したアプリケーションの下部に配置してください。"
- C1: 위반 시 "APIの利用を停止させていただく可能性があります。"
- C1: 보존·캐시에 관한 문구는 **없다**.
- Weak points: 날짜 없음

## A6 · P · 날짜 표기 없음
**Yahoo!ショッピングAPIのよくあるご質問** — Yahoo!デベロッパーネットワーク
https://developer.yahoo.co.jp/webapi/shopping/faq.html
- C1: 일 한도. "リクエスト数が上限（50000回）を超えている。対処方法：1日50,000リクエストを超える場合は、Client ID（アプリケーションID）を追加してご対応ください。" (에러 "Your Request was Forbidden"의 원인 설명)
- C1: "短時間に大量のリクエストが行われた場合には、利用を制限させていただくことがあります。…制限にかかる条件、および制限を解除するための条件は非公開とさせて頂いております。"
- C1: 데이터 보존·2차 이용에 관한 문답은 **없다**.
- Weak points: 날짜 없음. 50,000회 한도가 상품검색 v3에도 그대로 적용되는지는 문답에 API 구분이 없어 확정하지 못함

## A7 · — · unreadable: https://support.yahoo-net.jp/PccDeveloper/s/article/H000011080
"WebAPIの商用利用について" 헬프 문서. JavaScript 전용 페이지라 curl로는 본문이 나오지 않았다("このページを閲覧するにはJavaScriptをオンにする必要があります"). 검색(1회)으로도 본문 인용을 찾지 못했다. 상용 이용 조건은 **미확인**.

## A8 · P · 2012-06 (2026-10-24 아카이브 캡처)
**Rakuten Web Service: Terms of service（楽天ウェブサービス規約의 영문 참고 번역）** — Rakuten Group, Inc.
https://web.archive.org/web/20261024225638/https://webservice.rakuten.co.jp/guide/rule
- C2: 개편 뒤(2026-10-24 캡처)에도 규약 개정 이력은 "Enacted 14th December 2006 / Amended 25th April 2007 / Amended 8th June 2010 / Amended 28th June 2012" 그대로다. 2026년 개편에 맞춘 규약 개정은 이 캡처에 **없다**.
- C2: 보존 관련 조항은 제10조 1항 (9) 하나다. "Storing information obtained through the Web Services or the Applications in a place that enables the sharing of information with unspecified and/or many people." (금지 행위). 보존 기간(24시간 등)을 숫자로 정한 조항은 **없다**.
- C2: 제10조 1항 (7) "Regarding the information obtained through the Web Services and Applications (includes but is not limited to Product Information and user information), using them for purposes other than those determined separately by the Company, or copying or altering them in ways other than those determined separately by the Company" (금지).
- C2: 제10조 1항 (6) "To provide services using Web Services that competes or may compete against the Group" / (4) "To gain income by using the Web Services in ways other than Rakuten Affiliate (excludes the cases where the Company explicitly grants permission)" / (10) "Using the Web Services in an environment where only specific people can access (excludes the cases where the Company explicitly grants permission)".
- C2: 제8조 4항 "the Developer must provide a link to Rakuten Ichiba and any other websites specified by the Group… Additionally, the Developer must not provide links to websites other than the Rakuten Sites in the parts of the Applications where the Web Services has been used." 여러 쇼핑몰 가격을 한 화면에 나란히 보여 주는 구성과 부딪칠 수 있는 조항이다.
- C2: 제7조 3항 회사가 따로 정해 제한할 수 있는 항목에 "number of accesses, access times, frequency of information update"가 들어 있다. 제13조 크레딧 표시 "If required so by the Company, the Developer will display that the Product Information displayed on the Applications are supplied by the Group".
- C2: 제1조 2항 Product Information 정의에 가격이 포함된다("product names, store names, URLs, images, product descriptions, information prices").
- C3: 제2조 "The Developer must be Rakuten Members who have registered as a Rakuten Member following the procedures determined by the Company." / 제4조 1항 "The Company reserves the right to refuse the registration of the Developer information." 거주 국가 조건은 규약에 **없다**.
- Weak points: 영문 참고 번역이다. 페이지 스스로 "The Japanese original is the governing Terms of Service and this English translation shall have no legal force"라고 밝힌다. 일본어 원문은 읽지 못해 조문 일본어 인용이 없다. 아카이브 사본이라 2026-10-24 이후 개정 여부는 모른다. "unspecified and/or many people이 공유할 수 있는 곳"이 공개 웹 서비스의 서버 DB를 뜻하는지는 번역문만으로 가릴 수 없다

## A9 · — · unreadable: https://webservice.rakuten.co.jp/guide/rule
2026-11-26 재시도에서도 HTTP 503("アクセスが集中し、ページを閲覧しにくい状態になっております"). 같은 날 https://webservice.rakuten.co.jp/documentation 도 503. 일본어 원문은 라이브 사이트에서 확인하지 못했다.

## A10 · P · 2026-10 (2026-10-05 아카이브 캡처)
**Rakuten Web Service: API（API 목록, 영문 표시）** — Rakuten Group, Inc.
https://web.archive.org/web/20261005130824/https://webservice.rakuten.co.jp/documentation
- C2: 개편 뒤 시점 목록의 Rakuten Ichiba APIs는 5개다: Rakuten Ichiba Item Search API, Genre Search API, Attribute Search API, Ranking API, 그리고 "Item Price Navi API — Rakuten Product Search API enables developers to specify Keyword and Genre, and retrieve information of selling products on Rakuten Product." 즉 商品価格ナビ製品検索API(Product Search)는 목록에 **남아 있다** (링크: /documentation/ichiba-product-search).
- C2: Item Search 설명 "Developers are allowed to obtain the item information by specifying Keyword as well as to filter the search with Item Code, Shop Name or Genre Name." JAN으로 조회한다는 설명은 목록에 **없다**.
- C2: 이 목록 페이지에 요청 한도 수치, openapi 도메인, accessKey, Referer에 관한 문구는 **없다**.
- Weak points: 아카이브 사본. 목록에 있다고 해서 엔드포인트가 실제로 응답하는지는 확인하지 못함

## A11 · P · 2017-04 (2025-12-03 아카이브 캡처)
**商品価格ナビ製品検索API : 楽天プロダクト製品検索API(version:2017-04-26)** — Rakuten Group, Inc.
https://web.archive.org/web/20251203083021/https://webservice.rakuten.co.jp/documentation/ichiba-product-search
- C2: 입력 파라미터는 keyword, genreId, productId(楽天プロダクト製品ID), hits, page, sort, minPrice, maxPrice, orFlag, genreInformationFlag다. **JAN 파라미터가 없다.** 필수 조건은 "検索キーワード、ジャンルID、楽天プロダクト製品IDのいずれかが指定されていることが必須です。"
- C2: 출력에도 **JAN 필드가 없다**(페이지 전문에서 "JAN" 0건). 식별에 쓸 만한 필드는 productId, productName, productNo(型番), brandName, makerCode/makerName.
- C2: 가격은 범위와 평균으로 나온다: maxPrice, salesMaxPrice, usedExcludeMaxPrice, usedExcludeSalesMaxPrice, minPrice, salesMinPrice, usedExcludeMinPrice(中古を除く最低価格), usedExcludeSalesMinPrice(中古を除く購入可能な最低価格), averagePrice, 그리고 itemCount 등 상품 수.
- C2: 한도는 수치 없이 "※短い時間の間に大量に、同一のリクエストURLへアクセスすると、一定時間利用できなくなる場合がございます。" 와 429 에러("number of allowed requests has been exceeded for this API") 설명뿐이다.
- Weak points: **old** — 2026년 개편 전 캡처다(요청 URL이 `https://app.rakuten.co.jp/services/api/Product/Search/20170426`). 2026년 날짜를 요청했는데 아카이브가 2025-12-03 사본으로 돌려보냈다. 개편 뒤 파라미터·필드가 같은지는 미확인. keyword에 JAN 문자열을 넣는 방식이 통하는지는 문서에 없고 시험하지 못함

## A12 · P · 2012-06 (2023-12-11 아카이브 캡처)
**Rakuten Web Service: Terms of service（영문 참고 번역, 개편 전 캡처）** — Rakuten
https://web.archive.org/web/20231211122911/https://webservice.rakuten.co.jp/guide/rule
- C2: 개정 이력(마지막 "Amended 28th June 2012")과 제10조 1항 (9) 문구가 A8과 같다. 개편 전후로 규약 본문이 바뀌지 않았다는 A8의 관찰을 뒷받침한다.
- Weak points: derivative — A8과 같은 문서의 이전 캡처. 일본어 원문을 얻으려고 받았으나 역시 영문이었다

## A13 · C · 2021-04
**YahooJP ID with Japanese phone number** — WaniKani Community 포럼 글 (okino)
https://community.wanikani.com/t/yahoojp-id-with-japanese-phone-number/51068
- C3: 일본 밖 거주자의 경험담. "Since I don't live in Japan, it's impossible to get a Japanese phone number." / "For now, I just chose the option of receiving the authentication code using my other emails." 당시에는 휴대전화 대신 이메일로 인증 코드를 받는 선택지가 있었다는 뜻이지만, 그 방법으로 끝까지 됐는지는 스레드에 **나오지 않는다**. 답글 2개도 성공·실패를 확인해 주지 않는다.
- Weak points: old(2021-04, Yahoo! JAPAN의 SMS 인증 확대 이전일 수 있음), 1인 경험, 결과 미확인, 개발자 네트워크 앱 등록은 다루지 않음. WebFetch 요약으로 읽었다

## 읽지 않은 단서 (검색 결과에만 나온 것 — 근거로 쓰지 않음)

- C3 / Yahoo: 검색 결과 요약에 "signup requires a phone number … it isn't taking my American number"라는 포럼 인용과, fluctlight.net/jp_numbers(비거주자용 일본 번호 안내 위키)가 Yahoo! Japan을 전화번호 인증이 필요한 서비스로 든다는 내용이 있었다. 두 페이지 모두 열어 읽지 않았다.
- C3 / Yahoo: Yahoo 공식 헬프(support.yahoo-net.jp, 예: H000004666 휴대전화 번호 설정, H000010775 SMS 인증)는 A7과 같은 JS 전용 사이트라 읽지 못했다. 해외 번호 등록 가부에 대한 공식 문구는 **찾지 못했다**.
- C3 / 라쿠텐: 검색 4회 가운데 라쿠텐 회원 가입의 해외 거주 가부나 Rakuten Developers 앱 등록의 지역 제한을 말하는 공식·커뮤니티 글은 **나오지 않았다**. 제3자 안내 페이지 요약에는 가입 필수 항목이 메일 주소·사용자 ID·비밀번호·이름·후리가나·생일·성별이라고 나왔으나(주소·전화번호 없음) 읽어 확인하지 않았다.
- C2 / 라쿠텐: 제3자(Apify actor 설명) 요약에 "약 1 request/second" 한도와 applicationId + accessKey 요구가 나왔으나 공식 페이지에서는 수치를 확인하지 못했다.
- C1 / Yahoo: 이 API로 만든 가격 이력 사이트의 실례는 예산 때문에 찾아보지 않았다.


---

<!-- sources-B.md -->

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


---

<!-- sources-C.md -->

# Sources — 그룹 C (C7, C8)

조회일: 2026-11-26. 조회 횟수: 검색 12회 + 페이지·질의 13회 = 25회 (예산 약 14회 초과. 403·404·빈 검색 결과가 10회였음).
번호는 주장 번호(C1~C8)와 겹치지 않게 M으로 붙였다.

## M1 · — · unreadable: https://myfigurecollection.net/about/terms/
- C7: 자동 조회에 HTTP 403 Forbidden. 약관 원문을 읽지 못했다. 사이트가 자동화 클라이언트의 접근을 거절한다는 사실 자체는 확인됨(차단 주체가 Cloudflare인지는 확인하지 못함). 같은 사이트의 FAQ(`/about/faq/`)도 같은 이유로 재시도하지 않았다.

## M2 · — · unreadable: https://web.archive.org/web/2026/https://myfigurecollection.net/about/terms/
- C7: 조회 도구가 web.archive.org를 가져오지 못함. 약관 보관본도 읽지 못했다.

## M3 · P · 2026-11-26 (질의 시점)
**Wikidata Query Service / wbsearchentities 직접 질의** — Wikimedia Foundation
https://query.wikidata.org/sparql , https://www.wikidata.org/w/api.php?action=wbsearchentities
- C8: `Nendoroid` 엔티티 검색 결과는 2건뿐 — Q1319760 "Nendoroid"(설명 "Vinyl Figurines", 브랜드 항목)와 Q3874641 "Nendoroid Generation"(2012 video game). 개별 넨도로이드 상품 항목은 검색에 나오지 않음.
- C8: Q1319760을 가리키는 트리플은 18건, 그중 GTIN(P3962)을 가진 주어는 0건. 표본으로 본 15건은 전부 위키백과·커먼즈 sitelink(`schema:about`)였다. 즉 "넨도로이드의 한 제품"으로 모델링된 항목이 확인되지 않음.
- C8: `figma` 검색에서 피규어 관련은 Q307650 "Figma — brand of Japanese action figures" 브랜드 항목 1건.
- C8: Wikidata 전체에서 GTIN(P3962) 값이 `45` 또는 `49`(일본 GS1 접두)로 시작하는 항목은 445건(상품 종류 불문). 피규어 카탈로그로 쓸 수 있는 규모가 아님.
- Weak points: 18건 중 나머지 3건의 술어는 보지 못함. 스케일 피규어 일반(instance of figurine 등)에 대한 질의는 하지 않음. Wikidata 데이터의 라이선스(CC0) 페이지는 이번에 열람하지 않음.

## M4 · — · unreadable: https://docs.anilist.co/guide/terms-of-use
- C8: HTTP 403. 공식 문서 사이트의 약관 원문은 읽지 못함. 아래 M5(같은 문서의 GitBook 판)로 대체.

## M5 · P · 날짜 표시 없음
**Terms of Use (AniList APIv2 Docs, GitBook 판)** — AniList
https://anilist.gitbook.io/anilist-apiv2-docs/docs/guide/terms-of-use
- C8: (조회 도구의 요약, 원문 그대로가 아님) API는 비상업적 이용에 무료. 백업·데이터 저장 서비스로 쓰는 것은 엄격히 금지. 데이터의 hoarding 또는 mass collection은 엄격히 금지(순수 교육 목적 프로젝트는 완화). 같은 성격의 경쟁 서비스(애니·만화 리스트/트래커)는 금지이며, AniList API·계정과 지속적으로 연동하면 요청 시 허가될 수 있음.
- C8: 월 매출 $150 미만의 상업 앱은 별도 허가 없이 무료로 사용 가능, $150 초과는 상업 라이선스 필요(contact@anilist.co).
- C8: 귀속 표시(attribution)·AI 관련 조항은 이 페이지에 없음.
- Weak points: 조회 도구가 원문 대신 요약을 돌려줌(정확한 문구 미확인). GitBook 판이 현재 docs.anilist.co와 같은지 확인하지 못함. 날짜 없음. 속도 제한(분당 90회, 현재 저하 상태로 분당 30회)은 검색 결과 요약에서만 봤고 해당 페이지(`/guide/rate-limiting`)는 열람하지 않음.

## M6 · — · unreadable: https://www.goodsmile.com/en/sitepolicy
- C8: HTTP 404. 이 주소에 사이트 정책 페이지 없음.

## M7 · — · unreadable: https://www.kotobukiya.co.jp/sitepolicy/
- C8: HTTP 403. 고토부키야 사이트 정책을 읽지 못함.

## M8 · P · 날짜 표시 없음 (2026-11-26 열람)
**グッドスマイルカンパニー公式サイト 첫 화면** — Good Smile Company
https://www.goodsmile.com/ja
- C8: 푸터의 약관류 링크는 利用規約(`/ja/terms-of-use/`), 個人情報の取り扱いについて, 特定商取引法に関する表示, 会社概要뿐. "サイトポリシー" 링크 없음.
- C8: RSS·Atom·피드·API 링크가 페이지에 없음.
- C8: 상품 목록에는 상품명·메이커·가격·태그(再販, 特典付き)만 표시되고 JAN 코드는 없음. URL의 숫자(`/product/1144443`)는 사이트 내부 ID.
- C8: 저작권 표기는 "©️ GOOD SMILE COMPANY"뿐, 재이용 허락 문구 없음.
- Weak points: 조회 도구의 요약. 상품 상세 페이지에 JAN이 표시되는지는 확인하지 않음.

## M9 · P · 제정·개정일 표시 없음 (2026-11-26 열람)
**利用規約** — Good Smile Company
https://www.goodsmile.com/ja/terms-of-use/
- C8: 第19条(権利帰属) "当社ウェブサイトおよび本サービスに関する知的財産権等は全て当社または当社にライセンスを許諾している者に帰属しており". 상품 정보·이미지의 재이용을 허락하는 조항은 없음.
- C8: 第13条 禁止事項 중 관련 항목 — (2) "当社、他の会員、その他の第三者の知的財産権等、名誉その他の権利または利益を侵害する行為", (11) "当社のサーバーその他のコンピューターに不正にアクセスする行為", (16) "本サービスの運営を妨害するおそれのある行為", (17) "その他当社が不適切と判断する行為".
- C8: 複製·転載·二次利用, 자동화 수단·스크레이핑·크롤링, 상업 이용을 명시적으로 다룬 문구는 이 페이지에 없음(찾았으나 없음).
- Weak points: 조회 도구가 뽑아 준 발췌. 본문이 구매·결제·배송 중심이라 쇼핑몰 회원 약관 성격이며, 비회원의 사이트 열람·정보 재이용에 그대로 적용되는지 불분명. 날짜 없음.

## M10 · C · 원본 수집 기준 2023 (카드에 갱신일 표시 없음)
**p1atdev/pvc — PVC figure products dataset** — 개인(Hugging Face 사용자 p1atdev)
https://huggingface.co/datasets/p1atdev/pvc (데이터셋 카드: `/raw/main/README.md`)
- C8: 카드 메타데이터 `license: cc0-1.0`. 설명 원문 "This dataset contains product information of figure images scraped from multiple Web sites."
- C8: 하위 집합과 출처·건수 — goodsmile-figma 947, goodsmile-nendoroid 3378, goodsmile-scale 2203 (goodsmile.info `.../announced/2023`), kotobukiya 864 (kotobukiya.co.jp/en/product/figures/), myethos 95, spiritale 21, tokyofigures 394. 합계 7,902건.
- C8: 필드는 `id`, `title`, `image_urls`, `header_image_url`, `category`, `character`, `description(s)`, `price_value`, `price_unit`, `specs`, `details`. `details`의 키 목록에 `JANコード`, `Series`, `Character(s)`, `Manufacturer`, `Scale`, `Release Date`, `Price`, `Product Code`, `シリーズ`, `スケール`, `発売元`, `発売月`, `価格`, `商品コード` 등이 있음.
- Weak points: 제조사 사이트를 스크레이핑한 것이라 CC0 표기는 올린 사람의 선언일 뿐 원 권리자의 허락이 아님(M9 第19条는 권리를 GSC에 유보). 출처 URL이 2023년 발표분까지라 old. `JANコード` 키가 어느 하위 집합에 얼마나 채워져 있는지 확인하지 않음(키 이름이 일본어라 tokyofigures·spiritale 쪽일 가능성이 있으나 미확인). 작품·캐릭터는 정규화된 ID가 아니라 원문 문자열.

## M11 · P · 2019-08-08 ("Last Modified August 8, 2019")
**API License and Developer Agreement** — MyAnimeList
https://myanimelist.net/static/apiagreement.html
- C8: 스크레이핑 금지 — Section 4(i) "will not engage in any data scraping, web scraping, web harvesting, or other data extraction methods".
- C8: 상업 이용 제한 — Section 3(a)(xiv) "generate, charge or earn any fees, profits, revenues or other funds or amounts through Your Commercial Applications".
- C8: 일반 데이터의 캐시 기한 조항은 없음. 사용자 개인정보는 "only for the period of time reasonably necessary for the proper functioning of Your Applications", 삭제 요청 시 "within 24 hours". 속도 제한 수치는 없고 Section 6 "We also reserve the right to limit or restrict the amount of data usage associated with the API".
- C8: 경쟁 서비스 금지 조항은 없으나 Section 3(a)(ix) "use the API in any of Your Applications to imitate or attempt to impersonate the user experience of the Company Offering". 귀속은 "authorized by MyAnimeList" 예시.
- Weak points: 조회 도구의 발췌(조항 전체 문맥 미확인, 3(a)(xiv)는 금지 목록의 한 항목으로 읽힘). 2019년 문서 — 검색 결과에 2025-12-16자 MAL Terms of Use가 따로 보였으나 열람하지 않음. Jikan(비공식 MAL 스크레이퍼 API)의 조건은 조사하지 않음.

## M12 · V · 2026-03-27
**Best Apps for Tracking Your Action Figure Collection (2026)** — Ethan, iCollect Everything, LLC (자사 블로그)
https://www.icollecteverything.com/?p=1765
- C8(중앙 소스 없이 가는 방식의 선례): "The database is built from barcode scans and user contributions." 아주 희귀하거나 오래된 피규어는 "might need manual entry".
- C8: 스캔 대상은 "UPC barcodes on boxed figures", 수록 브랜드는 "Most major brands (Hasbro, NECA, McFarlane, Mattel, Funko) are in the database." 애니메이션·일본 피규어, JAN, CSV 가져오기·내보내기 언급은 글에 없음.
- Weak points: 판매자 본인의 홍보 글. 일본 피규어·JAN 적용 사례가 아님. 조회 도구의 발췌.

## 검색만 하고 얻은 것이 없는 조회 (재시도 방지용)

- C7 · MFC 공식 API(`api.php`)의 존재·폐지·현황: 검색 2회, MFC 측 문서·공지·관리자 발언을 하나도 찾지 못함. 결과에는 비공식 스크레이퍼 목록(vibehackers.io의 "myfigurecollection api" MCP 소개, pypi `mfc-scraper`, `tenji`, greasyfork "MFC Item Importer")만 나옴 — 열람하지 않은 단서.
- C7 · MFC 약관의 자동 접근·스크레이핑 조항: 검색 1회, MFC 약관 본문을 인용한 제3자 자료도 찾지 못함.
- C7 · MFC 컬렉션 CSV 내보내기: 검색 4회(영문 어휘를 바꿔 가며), MFC의 내보내기 기능을 설명하는 페이지를 하나도 찾지 못함. 기능이 없다는 근거도 아님 — 미확인.
- C8 · GSC 사이트 정책(일본어 검색) 1회: 공식 정책 페이지는 결과에 없음. 결과 제목으로만 본 단서: GameBusiness.jp 2026-10-25 "グッドスマイルカンパニー、公式ショップ不正アクセス発生により会員情報流出の可能性―サイトを閉鎖し原因確認作業へ" (열람하지 않음).
- C8 · 무료·상업 이용 가능한 JAN 상품 마스터 API, Open Products Facts의 일본 피규어 수록: 검색 1회, 해당하는 서비스나 약관을 찾지 못함. Go-UPC, barcodelookup.com은 결과에 이름만 나왔고 일본 피규어 수록·가격·약관은 확인하지 않음.
- C8 · 오픈 피규어 데이터셋(GitHub·Kaggle·Hugging Face): 검색 1회, 피규어 전용은 M10 하나뿐. manami-project/anime-offline-database(애니 메타데이터, 피규어 아님)와 Apify의 유료 스크레이퍼 액터는 열람하지 않은 단서.
- C8 · 바코드 스캔·사용자 입력형 컬렉션 앱: 검색 1회. Coleka, OTAHub, Collector: Figure Tracker는 앱스토어 결과로만 봤고 열람하지 않음. "MyFigureCollection에서 가져오기" 기능을 내세운 앱은 결과에 없음.

## 조사하지 못한 항목

- MFC: 약관·FAQ 원문, 콘텐츠 소유·라이선스 조항, 옛 API의 이력, 관리자의 API·제휴 관련 발언.
- 제조사: Kotobukiya(403), Alter, Max Factory, Bandai Spirits(魂ウェブ), Kaiyodo, FuRyu, SEGA, Taito의 약관·피드·JAN 표시 여부.
- 바코드 DB: Open Products Facts, UPCitemdb, barcodelookup, 일본 JANコード検索 서비스의 수록 범위·요금·재이용 조건. (Yahoo!·Rakuten 상품 API는 그룹 A 범위)
- 메타데이터 API: Jikan, Kitsu, AniDB, VNDB의 약관과 저장 허용 여부.

