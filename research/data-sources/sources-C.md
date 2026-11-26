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
