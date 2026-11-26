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
