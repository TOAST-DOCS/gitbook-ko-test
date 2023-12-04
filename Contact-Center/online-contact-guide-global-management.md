## Contact Center > Online Contact > 서비스 가이드 (상담관리) > 전체 관리

**전체 관리**는 서비스계약/해지, 조직관리, CTI설정 등 Contact Center를 이용하는 조직의 전반적인 설정 기능을 포함합니다.
계약 서비스 현황, 조직관리자, 회사정보 관리, CTI 관리, 권한 변경 로그 관리, 데이터 이관 메뉴로 구성되어 있습니다.


## 계약 서비스 현황

현재 조직에서 이용중인 서비스에 대한 관리와 요금, 조직 정보를 확인할 수 있는 메뉴입니다.

### 계약 현황

#### 1. 계약 현황 화면
![계약서비스현황_계약현황](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-global-management_img0010.png)

**계약 현황** 탭은 서비스를 추가하거나 내용 수정, 해지 등 서비스 계약 관련 기능을 사용할 수 있습니다.

**① 서비스 추가**

  - 현재 조직에 새로운 서비스를 추가하려면 **서비스 추가** 버튼을 클릭합니다.
  - 클릭 시 **서비스 추가 대화상자**가 실행됩니다.
  - 자세한 사용 방법은 아래 '2. 서비스 추가' 문단을 참고하십시오.

**② 기본정보**

  - **수정** 버튼을 클릭하여 등록된 서비스의 기본정보를 수정할 수 있습니다.

**③ 계약**

  - 서비스 추가 후 계약이 완료되지 않은 서비스는 **등록** 버튼으로, 계약이 완료된 서비스는 **수정**으로 표시됩니다.
  - 해당 버튼을 클릭하면 계약 내용을 이어서 작성하거나 수정할 수 있습니다.
  - 계약정보는 **하루에 1번만 수정 가능**합니다.

**④ 상태**

  - 토글 버튼으로 서비스의 사용여부를 변경할 수 있습니다.
  - 사용중지된 서비스는 이용이 불가하며 비용은 동일하게 과금 처리됩니다.

**⑤ 해지**
  
  - 서비스를 해지하려면 먼저 상태 토글 버튼을 클릭하여 **사용중지 처리**해야 합니다.
  - 이후 해지 버튼을 클릭하여 서비스를 해지할 수 있습니다.

#### 2. 서비스 추가
![계약서비스현황_서비스추가](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-global-management_img0020.png)

새로운 서비스를 추가하려면 아래의 순서로 처리합니다.

**① 서비스 추가**

- 추가할 서비스의 기본 정보를 입력한 후 다음 버튼을 클릭합니다.
- 입력이 필요한 항목은 아래와 같습니다.
    - 유형: 추가할 서비스의 유형(상담 관리, 이슈 관리)
    - 서비스 명: 사용할 서비스의 이름
    - 서비스 ID: 서비스 식별에 사용되는 ID(URL에 포함됨). 영문만 가능
    - 헬프센터 언어: 헬프센터 구성 시 사용할 언어 세트 설정
    > **※ 참고사항**
    >
    > 언어가 2개 이상 추가되었을 경우, 헬프센터 페이지에 언어 선택 드롭박스가 추가되어 언어별 헬프센터를 제공할 수 있습니다.
    > 언어 코드는 ISO 국제 표준 코드로 입력해야 합니다.
    >
    > <details markdown="1"> <!-- 국가 코드 목록 html -->
    > <summary><u>언어코드 목록 보기</u></summary>
    > <table>
    >   <thead>
    >   <tr>
    >   <th>ISO 언어명</th>
    >   <th>언어명</th>
    >   <th>언어 코드</th>
    >   </tr>
    >   </thead>
    >   <tbody>
    >   <tr>
    >   <td>Korean</td>
    >   <td>한국어</td>
    >   <td>ko</td>
    >   </tr>
    >   <tr>
    >   <td>Japanese</td>
    >   <td>日本語</td>
    >   <td>ja</td>
    >   </tr>
    >   <tr>
    >   <td>English</td>
    >   <td>English</td>
    >   <td>en</td>
    >   </tr>
    >   <tr>
    >   <td>Chinese</td>
    >   <td>中文</td>
    >   <td>zh</td>
    >   </tr>
    >   <tr>
    >   <td>Traditional Chinese</td>
    >   <td>中文(繁體)</td>
    >   <td>zh_TW</td>
    >   </tr>
    >   <tr>
    >   <td>Cantonese</td>
    >   <td>粵語</td>
    >   <td>yue</td>
    >   </tr>
    >   <tr>
    >   <td>Thai</td>
    >   <td>ไทย</td>
    >   <td>th</td>
    >   </tr>
    >   <tr>
    >   <td>Vietnamese</td>
    >   <td>Tiếng Việt</td>
    >   <td>vi</td>
    >   </tr>
    >   <tr>
    >   <td>Indonesian</td>
    >   <td>Indonesia</td>
    >   <td>id</td>
    >   </tr>
    >   <tr>
    >   <td>Malay</td>
    >   <td>Melayu</td>
    >   <td>ms</td>
    >   </tr>
    >   <tr>
    >   <td>Russian</td>
    >   <td>русский</td>
    >   <td>ru</td>
    >   </tr>
    >   <tr>
    >   <td>French</td>
    >   <td>français</td>
    >   <td>fr</td>
    >   </tr>
    >   <tr>
    >   <td>German</td>
    >   <td>Deutsch</td>
    >   <td>de</td>
    >   </tr>
    >   <tr>
    >   <td>Spanish, Castilian</td>
    >   <td>Español</td>
    >   <td>es</td>
    >   </tr>
    >   <tr>
    >   <td>Spanish (Latin America)</td>
    >   <td>Español(Latinoamérica)</td>
    >   <td>es_LA</td>
    >   </tr>
    >   <tr>
    >   <td>Portuguese (Portugal)</td>
    >   <td>Português</td>
    >   <td>pt</td>
    >   </tr>
    >   <tr>
    >   <td>Portuguese (Brazil)</td>
    >   <td>Português(Brasil)</td>
    >   <td>pt_BR</td>
    >   </tr>
    >   <tr>
    >   <td>Italian</td>
    >   <td>Italiano</td>
    >   <td>it</td>
    >   </tr>
    >   <tr>
    >   <td>Arabic</td>
    >   <td>العربية</td>
    >   <td>ar</td>
    >   </tr>
    >   <tr>
    >   <td>Turkish</td>
    >   <td>Türkçe</td>
    >   <td>tr</td>
    >   </tr>
    >   <tr>
    >   <td>Dutch, Flemish</td>
    >   <td>Nederlands</td>
    >   <td>nl</td>
    >   </tr>
    >   <tr>
    >   <td>Polish</td>
    >   <td>polski</td>
    >   <td>pl</td>
    >   </tr>
    >   <tr>
    >   <td>Abkhazian</td>
    >   <td>аҧсшәа</td>
    >   <td>ab</td>
    >   </tr>
    >   <tr>
    >   <td>Afar</td>
    >   <td>Afaraf</td>
    >   <td>aa</td>
    >   </tr>
    >   <tr>
    >   <td>Aragonese</td>
    >   <td>aragonés</td>
    >   <td>an</td>
    >   </tr>
    >   <tr>
    >   <td>Assamese</td>
    >   <td>অসমীয়া</td>
    >   <td>as</td>
    >   </tr>
    >   <tr>
    >   <td>Avaric,Avar</td>
    >   <td>авар мацӀ</td>
    >   <td>av</td>
    >   </tr>
    >   <tr>
    >   <td>Avestan</td>
    >   <td>avesta</td>
    >   <td>ae</td>
    >   </tr>
    >   <tr>
    >   <td>Aymara</td>
    >   <td>aymar aru</td>
    >   <td>ay</td>
    >   </tr>
    >   <tr>
    >   <td>Bambara</td>
    >   <td>bamanankan</td>
    >   <td>bm</td>
    >   </tr>
    >   <tr>
    >   <td>Bislama</td>
    >   <td>Bislama</td>
    >   <td>bi</td>
    >   </tr>
    >   <tr>
    >   <td>Croatian</td>
    >   <td>hrvatsk</td>
    >   <td>hr</td>
    >   </tr>
    >   <tr>
    >   <td>Bashkir</td>
    >   <td>башҡорт теле</td>
    >   <td>ba</td>
    >   </tr>
    >   <tr>
    >   <td>Acoli</td>
    >   <td>Lwo</td>
    >   <td>ach</td>
    >   </tr>
    >   <tr>
    >   <td>Afrikaans</td>
    >   <td>Afrikaans</td>
    >   <td>af</td>
    >   </tr>
    >   <tr>
    >   <td>Akan</td>
    >   <td>Akan</td>
    >   <td>ak</td>
    >   </tr>
    >   <tr>
    >   <td>Chamorro</td>
    >   <td>Chamoru</td>
    >   <td>ch</td>
    >   </tr>
    >   <tr>
    >   <td>Azerbaijani</td>
    >   <td>Azərbaycan</td>
    >   <td>az</td>
    >   </tr>
    >   <tr>
    >   <td>Chechen</td>
    >   <td>нохчийн мотт</td>
    >   <td>ce</td>
    >   </tr>
    >   <tr>
    >   <td>Balinese</td>
    >   <td>Basa Bali</td>
    >   <td>ban</td>
    >   </tr>
    >   <tr>
    >   <td>Sundanese</td>
    >   <td>Basa Sunda</td>
    >   <td>su</td>
    >   </tr>
    >   <tr>
    >   <td>Cebuano</td>
    >   <td>Binisayâ</td>
    >   <td>ceb</td>
    >   </tr>
    >   <tr>
    >   <td>Chuvash</td>
    >   <td>чӑваш чӗлхи</td>
    >   <td>cv</td>
    >   </tr>
    >   <tr>
    >   <td>Bosnian</td>
    >   <td>bosanski</td>
    >   <td>bs</td>
    >   </tr>
    >   <tr>
    >   <td>Cornish</td>
    >   <td>Kernewek</td>
    >   <td>kw</td>
    >   </tr>
    >   <tr>
    >   <td>Breton</td>
    >   <td>Brezhoneg</td>
    >   <td>br</td>
    >   </tr>
    >   <tr>
    >   <td>Catalan; Valencian</td>
    >   <td>català</td>
    >   <td>ca</td>
    >   </tr>
    >   <tr>
    >   <td>Cree</td>
    >   <td>ᓀᐦᐃᔭᐍᐏᐣ</td>
    >   <td>cr</td>
    >   </tr>
    >   <tr>
    >   <td>Czech</td>
    >   <td>čeština</td>
    >   <td>cs</td>
    >   </tr>
    >   <tr>
    >   <td>Shona</td>
    >   <td>chiShona</td>
    >   <td>sn</td>
    >   </tr>
    >   <tr>
    >   <td>Corsican</td>
    >   <td>Corsu</td>
    >   <td>co</td>
    >   </tr>
    >   <tr>
    >   <td>Welsh</td>
    >   <td>Cymraeg</td>
    >   <td>cy</td>
    >   </tr>
    >   <tr>
    >   <td>Divehi, Dhivehi, Maldivian</td>
    >   <td>ދިވެހި</td>
    >   <td>dv</td>
    >   </tr>
    >   <tr>
    >   <td>Danish</td>
    >   <td>dansk</td>
    >   <td>da</td>
    >   </tr>
    >   <tr>
    >   <td>Dzongkha</td>
    >   <td>རྫོང་ཁ</td>
    >   <td>dz</td>
    >   </tr>
    >   <tr>
    >   <td>Yoruba</td>
    >   <td>Èdè Yorùbá</td>
    >   <td>yo</td>
    >   </tr>
    >   <tr>
    >   <td>Estonian</td>
    >   <td>eesti</td>
    >   <td>et</td>
    >   </tr>
    >   <tr>
    >   <td>Esperanto</td>
    >   <td>Esperanto</td>
    >   <td>eo</td>
    >   </tr>
    >   <tr>
    >   <td>Basque</td>
    >   <td>euskara</td>
    >   <td>eu</td>
    >   </tr>
    >   <tr>
    >   <td>Ewe</td>
    >   <td>Èʋegbe</td>
    >   <td>ee</td>
    >   </tr>
    >   <tr>
    >   <td>Tagalog</td>
    >   <td>Tagalog</td>
    >   <td>tl</td>
    >   </tr>
    >   <tr>
    >   <td>Filipino; Pilipino</td>
    >   <td>Filipino</td>
    >   <td>fil</td>
    >   </tr>
    >   <tr>
    >   <td>Fijian</td>
    >   <td>vosa Vakaviti</td>
    >   <td>fj</td>
    >   </tr>
    >   <tr>
    >   <td>Faroese</td>
    >   <td>føroyskt</td>
    >   <td>fo</td>
    >   </tr>
    >   <tr>
    >   <td>Western Frisian</td>
    >   <td>Frysk</td>
    >   <td>fy</td>
    >   </tr>
    >   <tr>
    >   <td>Fulah</td>
    >   <td>Pular</td>
    >   <td>ff</td>
    >   </tr>
    >   <tr>
    >   <td>Ga</td>
    >   <td>Gã</td>
    >   <td>gaa</td>
    >   </tr>
    >   <tr>
    >   <td>Irish</td>
    >   <td>Gaeilge</td>
    >   <td>ga</td>
    >   </tr>
    >   <tr>
    >   <td>Gaelic; Scottish Gaelic</td>
    >   <td>Gàidhlig</td>
    >   <td>gd</td>
    >   </tr>
    >   <tr>
    >   <td>Galician</td>
    >   <td>galego</td>
    >   <td>gl</td>
    >   </tr>
    >   <tr>
    >   <td>Guarani</td>
    >   <td>Avañe'ẽ</td>
    >   <td>gn</td>
    >   </tr>
    >   <tr>
    >   <td>Haitian; Haitian Creole</td>
    >   <td>Kreyòl ayisyen</td>
    >   <td>ht</td>
    >   </tr>
    >   <tr>
    >   <td>Hausa</td>
    >   <td>Hausa</td>
    >   <td>ha</td>
    >   </tr>
    >   <tr>
    >   <td>Hawaiian</td>
    >   <td>ʻŌlelo Hawaiʻi</td>
    >   <td>haw</td>
    >   </tr>
    >   <tr>
    >   <td>Bemba</td>
    >   <td>Chibemba</td>
    >   <td>bem</td>
    >   </tr>
    >   <tr>
    >   <td>Igbo</td>
    >   <td>Igbo</td>
    >   <td>ig</td>
    >   </tr>
    >   <tr>
    >   <td>Herero</td>
    >   <td>Otjiherero</td>
    >   <td>hz</td>
    >   </tr>
    >   <tr>
    >   <td>Rundi</td>
    >   <td>Ikirundi</td>
    >   <td>rn</td>
    >   </tr>
    >   <tr>
    >   <td>Interlingua (International Auxiliary Language Association)</td>
    >   <td>Interlingua</td>
    >   <td>ia</td>
    >   </tr>
    >   <tr>
    >   <td>Hiri Motu</td>
    >   <td>Hiri Motu</td>
    >   <td>ho</td>
    >   </tr>
    >   <tr>
    >   <td>Xhosa</td>
    >   <td>isiXhosa</td>
    >   <td>xh</td>
    >   </tr>
    >   <tr>
    >   <td>Zulu</td>
    >   <td>isiZulu</td>
    >   <td>zu</td>
    >   </tr>
    >   <tr>
    >   <td>Icelandic</td>
    >   <td>íslenska</td>
    >   <td>is</td>
    >   </tr>
    >   <tr>
    >   <td>Javanese</td>
    >   <td>Jawa</td>
    >   <td>jv</td>
    >   </tr>
    >   <tr>
    >   <td>Interlingue, Occidental</td>
    >   <td>Occidental</td>
    >   <td>ie</td>
    >   </tr>
    >   <tr>
    >   <td>Kinyarwanda</td>
    >   <td>Ikinyarwanda</td>
    >   <td>rw</td>
    >   </tr>
    >   <tr>
    >   <td>Swahili</td>
    >   <td>Kiswahili</td>
    >   <td>sw</td>
    >   </tr>
    >   <tr>
    >   <td>Klingon; tlhIngan-Hol</td>
    >   <td>Klingon</td>
    >   <td>tlh</td>
    >   </tr>
    >   <tr>
    >   <td>Inupiaq</td>
    >   <td>Iñupiaq</td>
    >   <td>ik</td>
    >   </tr>
    >   <tr>
    >   <td>Kongo</td>
    >   <td>Kikongo</td>
    >   <td>kg</td>
    >   </tr>
    >   <tr>
    >   <td>Ido</td>
    >   <td>Ido</td>
    >   <td>io</td>
    >   </tr>
    >   <tr>
    >   <td>Latin</td>
    >   <td>Latin</td>
    >   <td>la</td>
    >   </tr>
    >   <tr>
    >   <td>Inuktitut</td>
    >   <td>ᐃᓄᒃᑎᑐᑦ</td>
    >   <td>iu</td>
    >   </tr>
    >   <tr>
    >   <td>Latvian</td>
    >   <td>latviešu</td>
    >   <td>lv</td>
    >   </tr>
    >   <tr>
    >   <td>Tonga (Tonga Islands)</td>
    >   <td>lea fakatonga</td>
    >   <td>to</td>
    >   </tr>
    >   <tr>
    >   <td>Lithuanian</td>
    >   <td>lietuvių</td>
    >   <td>lt</td>
    >   </tr>
    >   <tr>
    >   <td>Kalaallisut, Greenlandic</td>
    >   <td>kalaallisut</td>
    >   <td>kl</td>
    >   </tr>
    >   <tr>
    >   <td>Lingala</td>
    >   <td>lingála</td>
    >   <td>ln</td>
    >   </tr>
    >   <tr>
    >   <td>Lozi</td>
    >   <td>Lozi</td>
    >   <td>loz</td>
    >   </tr>
    >   <tr>
    >   <td>Kanuri</td>
    >   <td>Kanuri</td>
    >   <td>kr</td>
    >   </tr>
    >   <tr>
    >   <td>Luba-Lulua</td>
    >   <td>Tshiluba</td>
    >   <td>lua</td>
    >   </tr>
    >   <tr>
    >   <td>Kashmiri</td>
    >   <td>कॉशुर</td>
    >   <td>ks</td>
    >   </tr>
    >   <tr>
    >   <td>Ganda</td>
    >   <td>Luganda</td>
    >   <td>lg</td>
    >   </tr>
    >   <tr>
    >   <td>Hungarian</td>
    >   <td>magyar</td>
    >   <td>hu</td>
    >   </tr>
    >   <tr>
    >   <td>Malagasy</td>
    >   <td>Malagasy</td>
    >   <td>mg</td>
    >   </tr>
    >   <tr>
    >   <td>Kikuyu, Gikuyu</td>
    >   <td>Gĩkũyũ</td>
    >   <td>ki</td>
    >   </tr>
    >   <tr>
    >   <td>Maltese</td>
    >   <td>Malti</td>
    >   <td>mt</td>
    >   </tr>
    >   <tr>
    >   <td>Norwegian</td>
    >   <td>norsk</td>
    >   <td>no</td>
    >   </tr>
    >   <tr>
    >   <td>Komi</td>
    >   <td>коми кыв</td>
    >   <td>kv</td>
    >   </tr>
    >   <tr>
    >   <td>Norwegian Nynorsk; Nynorsk, Norwegian</td>
    >   <td>norsk nynorsk</td>
    >   <td>nn</td>
    >   </tr>
    >   <tr>
    >   <td>Pedi; Sepedi; Northern Sotho</td>
    >   <td>Northern Sotho</td>
    >   <td>nso</td>
    >   </tr>
    >   <tr>
    >   <td>Chichewa; Chewa; Nyanja</td>
    >   <td>chinyanja</td>
    >   <td>ny</td>
    >   </tr>
    >   <tr>
    >   <td>Kurdish</td>
    >   <td>Kurdî</td>
    >   <td>ku</td>
    >   </tr>
    >   <tr>
    >   <td>Uzbek</td>
    >   <td>Oʻzbek</td>
    >   <td>uz</td>
    >   </tr>
    >   <tr>
    >   <td>Kuanyama, Kwanyama</td>
    >   <td>Kuanyama</td>
    >   <td>kj</td>
    >   </tr>
    >   <tr>
    >   <td>Occitan</td>
    >   <td>Occitan</td>
    >   <td>oc</td>
    >   </tr>
    >   <tr>
    >   <td>Oromo</td>
    >   <td>Oromoo</td>
    >   <td>om</td>
    >   </tr>
    >   <tr>
    >   <td>Luxembourgish, Letzeburgesch</td>
    >   <td>Lëtzebuergesch</td>
    >   <td>lb</td>
    >   </tr>
    >   <tr>
    >   <td>Romanian; Moldavian; Moldovan</td>
    >   <td>Română</td>
    >   <td>ro</td>
    >   </tr>
    >   <tr>
    >   <td>Romansh</td>
    >   <td>Rumantsch</td>
    >   <td>rm</td>
    >   </tr>
    >   <tr>
    >   <td>Limburgan, Limburger, Limburgish</td>
    >   <td>Limburgs</td>
    >   <td>li</td>
    >   </tr>
    >   <tr>
    >   <td>Quechua</td>
    >   <td>Runa Simi</td>
    >   <td>qu</td>
    >   </tr>
    >   <tr>
    >   <td>Nyankole</td>
    >   <td>Runyankore</td>
    >   <td>nyn</td>
    >   </tr>
    >   <tr>
    >   <td>Albanian</td>
    >   <td>Shqip</td>
    >   <td>sq</td>
    >   </tr>
    >   <tr>
    >   <td>Luba-Katanga</td>
    >   <td>Kiluba</td>
    >   <td>lu</td>
    >   </tr>
    >   <tr>
    >   <td>Slovak</td>
    >   <td>slovenčina</td>
    >   <td>sk</td>
    >   </tr>
    >   <tr>
    >   <td>Slovenian</td>
    >   <td>slovenščina</td>
    >   <td>sl</td>
    >   </tr>
    >   <tr>
    >   <td>Manx</td>
    >   <td>Gaelg</td>
    >   <td>gv</td>
    >   </tr>
    >   <tr>
    >   <td>Somali</td>
    >   <td>Soomaali</td>
    >   <td>so</td>
    >   </tr>
    >   <tr>
    >   <td>Sotho, Southern</td>
    >   <td>Sesotho</td>
    >   <td>st</td>
    >   </tr>
    >   <tr>
    >   <td>Serbian</td>
    >   <td>српски</td>
    >   <td>sr</td>
    >   </tr>
    >   <tr>
    >   <td>Serbian (Montenegro)</td>
    >   <td>srpski(Crna Gora)</td>
    >   <td>sr_ME</td>
    >   </tr>
    >   <tr>
    >   <td>Serbian (Latin)</td>
    >   <td>srpski(latinica)</td>
    >   <td>sr_LN</td>
    >   </tr>
    >   <tr>
    >   <td>Finnish</td>
    >   <td>suomi</td>
    >   <td>fi</td>
    >   </tr>
    >   <tr>
    >   <td>Swedish</td>
    >   <td>svenska</td>
    >   <td>sv</td>
    >   </tr>
    >   <tr>
    >   <td>Maori</td>
    >   <td>te reo Māori</td>
    >   <td>mi</td>
    >   </tr>
    >   <tr>
    >   <td>Tswana</td>
    >   <td>Setswana</td>
    >   <td>tn</td>
    >   </tr>
    >   <tr>
    >   <td>Marshallese</td>
    >   <td>Kajin M̧ajeļ</td>
    >   <td>mh</td>
    >   </tr>
    >   <tr>
    >   <td>Tumbuka</td>
    >   <td>Tumbuka</td>
    >   <td>tum</td>
    >   </tr>
    >   <tr>
    >   <td>Turkmen</td>
    >   <td>türkmen dili</td>
    >   <td>tk</td>
    >   </tr>
    >   <tr>
    >   <td>Nauru</td>
    >   <td>Dorerin Naoero</td>
    >   <td>na</td>
    >   </tr>
    >   <tr>
    >   <td>Twi</td>
    >   <td>Twi</td>
    >   <td>tw</td>
    >   </tr>
    >   <tr>
    >   <td>Navajo, Navaho</td>
    >   <td>Diné bizaad</td>
    >   <td>nv</td>
    >   </tr>
    >   <tr>
    >   <td>Wolof</td>
    >   <td>Wolof</td>
    >   <td>wo</td>
    >   </tr>
    >   <tr>
    >   <td>Greek, Modern (1453–)</td>
    >   <td>Ελληνικά</td>
    >   <td>el</td>
    >   </tr>
    >   <tr>
    >   <td>North Ndebele</td>
    >   <td>isiNdebele</td>
    >   <td>nd</td>
    >   </tr>
    >   <tr>
    >   <td>Belarusian</td>
    >   <td>беларуская</td>
    >   <td>be</td>
    >   </tr>
    >   <tr>
    >   <td>Bulgarian</td>
    >   <td>български</td>
    >   <td>bg</td>
    >   </tr>
    >   <tr>
    >   <td>Ndonga</td>
    >   <td>Owambo</td>
    >   <td>ng</td>
    >   </tr>
    >   <tr>
    >   <td>Kirghiz, Kyrgyz</td>
    >   <td>кыргызча</td>
    >   <td>ky</td>
    >   </tr>
    >   <tr>
    >   <td>Norwegian Bokmål</td>
    >   <td>Norsk Bokmål</td>
    >   <td>nb</td>
    >   </tr>
    >   <tr>
    >   <td>Kazakh</td>
    >   <td>қазақ тілі</td>
    >   <td>kk</td>
    >   </tr>
    >   <tr>
    >   <td>Macedonian</td>
    >   <td>македонски</td>
    >   <td>mk</td>
    >   </tr>
    >   <tr>
    >   <td>Sichuan Yi, Nuosu</td>
    >   <td>ꆈꌠ꒿</td>
    >   <td>ii</td>
    >   </tr>
    >   <tr>
    >   <td>Mongolian</td>
    >   <td>монгол</td>
    >   <td>mn</td>
    >   </tr>
    >   <tr>
    >   <td>South Ndebele</td>
    >   <td>isiNdebele</td>
    >   <td>nr</td>
    >   </tr>
    >   <tr>
    >   <td>Tatar</td>
    >   <td>татар</td>
    >   <td>tt</td>
    >   </tr>
    >   <tr>
    >   <td>Ojibwa</td>
    >   <td>ᐊᓂᔑᓈᐯᒧᐎᓐ</td>
    >   <td>oj</td>
    >   </tr>
    >   <tr>
    >   <td>Tajik</td>
    >   <td>тоҷикӣ</td>
    >   <td>tg</td>
    >   </tr>
    >   <tr>
    >   <td>Church&nbsp;Slavic, Old Slavonic, Church Slavonic, Old Bulgarian,&  nbsp;   Old&nbsp; hurch&  nbsp;> Slavonic</td>
    >   <td>ѩзыкъ словѣньскъ</td>
    >   <td>cu</td>
    >   </tr>
    >   <tr>
    >   <td>Ukrainian</td>
    >   <td>Українська</td>
    >   <td>uk</td>
    >   </tr>
    >   <tr>
    >   <td>Georgian</td>
    >   <td>ქართული</td>
    >   <td>ka</td>
    >   </tr>
    >   <tr>
    >   <td>Armenian</td>
    >   <td>Հայերեն</td>
    >   <td>hy</td>
    >   </tr>
    >   <tr>
    >   <td>Ossetian, Ossetic</td>
    >   <td>ирон ӕвзаг</td>
    >   <td>os</td>
    >   </tr>
    >   <tr>
    >   <td>Yiddish</td>
    >   <td>ייִדיש</td>
    >   <td>yi</td>
    >   </tr>
    >   <tr>
    >   <td>Hebrew</td>
    >   <td>עברית</td>
    >   <td>he</td>
    >   </tr>
    >   <tr>
    >   <td>Pali</td>
    >   <td>पालि</td>
    >   <td>pi</td>
    >   </tr>
    >   <tr>
    >   <td>Uighur, Uyghur</td>
    >   <td>ئۇيغۇرچە‎</td>
    >   <td>ug</td>
    >   </tr>
    >   <tr>
    >   <td>Urdu</td>
    >   <td>اردو</td>
    >   <td>ur</td>
    >   </tr>
    >   <tr>
    >   <td>Pashto, Pushto</td>
    >   <td>پښتو</td>
    >   <td>ps</td>
    >   </tr>
    >   <tr>
    >   <td>Sindhi</td>
    >   <td>سنڌي</td>
    >   <td>sd</td>
    >   </tr>
    >   <tr>
    >   <td>Persian</td>
    >   <td>فارسی</td>
    >   <td>fa</td>
    >   </tr>
    >   <tr>
    >   <td>Tigrinya</td>
    >   <td>ትግርኛ</td>
    >   <td>ti</td>
    >   </tr>
    >   <tr>
    >   <td>Amharic</td>
    >   <td>አማርኛ</td>
    >   <td>am</td>
    >   </tr>
    >   <tr>
    >   <td>Nepali</td>
    >   <td>नेपाली</td>
    >   <td>ne</td>
    >   </tr>
    >   <tr>
    >   <td>Marathi</td>
    >   <td>मराठी</td>
    >   <td>mr</td>
    >   </tr>
    >   <tr>
    >   <td>Hindi</td>
    >   <td>हिन्दी</td>
    >   <td>hi</td>
    >   </tr>
    >   <tr>
    >   <td>Sanskrit</td>
    >   <td>संस्कृतम्,&nbsp;𑌸𑌂𑌸𑍍𑌕𑍃𑌤𑌮𑍍</td>
    >   <td>sa</td>
    >   </tr>
    >   <tr>
    >   <td>Bengali</td>
    >   <td>বাংলা</td>
    >   <td>bn</td>
    >   </tr>
    >   <tr>
    >   <td>Sardinian</td>
    >   <td>sardu</td>
    >   <td>sc</td>
    >   </tr>
    >   <tr>
    >   <td>Punjabi, Panjabi</td>
    >   <td>ਪੰਜਾਬੀ</td>
    >   <td>pa</td>
    >   </tr>
    >   <tr>
    >   <td>Gujarati</td>
    >   <td>ગુજરાતી</td>
    >   <td>gu</td>
    >   </tr>
    >   <tr>
    >   <td>Northern Sami</td>
    >   <td>Davvisámegiella</td>
    >   <td>se</td>
    >   </tr>
    >   <tr>
    >   <td>Oriya</td>
    >   <td>ଓଡ଼ିଆ</td>
    >   <td>or</td>
    >   </tr>
    >   <tr>
    >   <td>Samoan</td>
    >   <td>gagana fa'a Samoa</td>
    >   <td>sm</td>
    >   </tr>
    >   <tr>
    >   <td>Sango</td>
    >   <td>yângâ tî sängö</td>
    >   <td>sg</td>
    >   </tr>
    >   <tr>
    >   <td>Tamil</td>
    >   <td>தமிழ்</td>
    >   <td>ta</td>
    >   </tr>
    >   <tr>
    >   <td>Telugu</td>
    >   <td>తెలుగు</td>
    >   <td>te</td>
    >   </tr>
    >   <tr>
    >   <td>Kannada</td>
    >   <td>ಕನ್ನಡ</td>
    >   <td>kn</td>
    >   </tr>
    >   <tr>
    >   <td>Malayalam</td>
    >   <td>മലയാളം</td>
    >   <td>ml</td>
    >   </tr>
    >   <tr>
    >   <td>Sinhala, Sinhalese</td>
    >   <td>සිංහල</td>
    >   <td>si</td>
    >   </tr>
    >   <tr>
    >   <td>Lao</td>
    >   <td>ລາວ</td>
    >   <td>lo</td>
    >   </tr>
    >   <tr>
    >   <td>Burmese</td>
    >   <td>မြန်မာ</td>
    >   <td>my</td>
    >   </tr>
    >   <tr>
    >   <td>Central Khmer</td>
    >   <td>ខ្មែរ</td>
    >   <td>km</td>
    >   </tr>
    >   <tr>
    >   <td>Cherokee</td>
    >   <td>ᏣᎳᎩ</td>
    >   <td>chr</td>
    >   </tr>
    >   <tr>
    >   <td>Swati</td>
    >   <td>SiSwati</td>
    >   <td>ss</td>
    >   </tr>
    >   <tr>
    >   <td>Tibetan</td>
    >   <td>བོད་ཡིག</td>
    >   <td>bo</td>
    >   </tr>
    >   <tr>
    >   <td>Tsonga</td>
    >   <td>Xitsonga</td>
    >   <td>ts</td>
    >   </tr>
    >   <tr>
    >   <td>Tahitian</td>
    >   <td>Reo Tahiti</td>
    >   <td>ty</td>
    >   </tr>
    >   <tr>
    >   <td>Venda</td>
    >   <td>Tshivenḓa</td>
    >   <td>ve</td>
    >   </tr>
    >   <tr>
    >   <td>Volapük</td>
    >   <td>Volapük</td>
    >   <td>vo</td>
    >   </tr>
    >   <tr>
    >   <td>Walloon</td>
    >   <td>Walon</td>
    >   <td>wa</td>
    >   </tr>
    >   <tr>
    >   <td>Zhuang, Chuang</td>
    >   <td>Saɯ cueŋƅ</td>
    >   <td>za</td>
    >   </tr>
    >   </tbody>
    >   </table>
    >   </details>
    - 타임 존: 헬프센터에 설정되는 시간대
    - 서비스 배너: Online Contact GNB에서의 서비스 탭 이미지, 채팅 시 상담원의 프로필 사진으로 적용
    - 에디터 타입: 해당 서비스에서 사용할 에디터 타입(HTML/TEXT)

**③ 계약 상세 내역**

- Online Contact에서 제공하는 상담 기능들에 대한 **사용 여부**를 선택합니다.
- 기능별 사용여부를 설정한 후 우측의 사용자 수, 처리 건 수 등을 입력하면 **예상 비용**을 확인할 수 있습니다.
- 설정 후 **계약** 버튼을 클릭하면 서비스 계약이 완료됩니다.

### 요금 현황
![계약서비스현황_요금현황](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-global-management_img0051.png)

**요금 현황** 탭에서는 전체, 서비스 유형별, 개별 서비스별 월별 청구 요금을 **①** 검색하여 조회할 수 있습니다.
개별 서비스를 선택하여 조회하면 **②** 서비스 상태가 함께 표시됩니다.

✔ **\[FAQ 바로가기]** [과금 기준은 어떻게 되나요?](https://nhn-contact.oc.nhncloud.com/oc/hc/article/99/)

✔ **\[FAQ 바로가기]** [요금은 언제 어떻게 결제되나요?](https://nhn-contact.oc.nhncloud.com/oc/hc/article/67/)

### 조직 정보
![계약서비스현황_조직정보](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-global-management_img0060.png)

**조직 정보** 탭에서는 Online Contact 서비스를 이용하고 있는 **NHN Cloud 조직 정보**와, Online Contact 내부의 계약 서비스들을 관리하는 **Online Contact 조직 정보**를 확인할 수 있습니다.

**① NHN Cloud 조직 정보**
NHN Cloud 조직 정보에서 확인할 수 있는 내용은 아래와 같습니다.
아래 정보는 모두 **NHN Cloud Console → 조직 설정 → 조직 기본 설정** 탭에서도 확인할 수 있으며, 조직 이름, 도메인은 해당 탭에서 수정할 수 있습니다.

- NHN Cloud 조직 이름: 조직 생성 시 설정한 이름
- NHN Cloud 조직 ID: 조직 생성 시 각 조직마다 부여되는 고유한 ID. Online Contact Open API 사용 시 필요한 인증 토큰 생성에 사용 
- NHN Cloud 조직 도메인: 조직 생성 후 서비스 선택 시 설정한 도메인 이름

**② OC(Online Contact) 조직 정보**
OC 조직 정보에서 확인할 수 있는 내용은 아래와 같습니다.
**조직 Key**의 경우 API Key 변경 버튼을 통해 변경 가능하며, **Online Contact URL**은 NHN Cloud 조직 도메인을 이용하여 생성되므로 조직 도메인 변경 시 함께 변경됩니다.

- OC 조직 Key: 서비스 등록/수정/삭제 등 조직 관리 차원에서 수행되는 행위를 Online Contact 외부에서 API를 통해 처리하고자 할 때 인증 단계에서 사용되는 Key
- OC URL: Online Contact 접속 URL로, https://**{조직 도메인}**.oc.nhncloud.com 형식으로 생성됨


## 조직관리자
![계약서비스현황_조직관리자](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-global-management_img0070.png)

**조직관리자**는 Online Contact의 전체관리 메뉴 권한 및 상담원 추가/삭제 권한을 가집니다.

조직관리자 메뉴에서는 IAM 회원으로 등록되지 않은 상담원을 초대하거나 상담원 중 조직관리자로 추가할 수 있습니다. 조직관리자 권한만으로는 상담 기능과 서비스 관리 기능을 이용할 수 없으므로 상담 권한이 필요하거나 서비스를 초기에 구성할 경우 **서비스 관리 → 상담원** 메뉴에서 관리자 또는 상담원 권한을 추가해야 합니다.

조직관리자 및 상담원을 등록하려면 IAM 회원으로 등록되어 있어야 합니다.

✔ **\[FAQ 바로가기]** [권한의 종류와 차이점을 알고 싶습니다.](https://nhn-contact.oc.nhncloud.com/oc/hc/article/36/)

**① 회원 초대**

- 조직관리자를 추가하기 전, 해당 담당자가 IAM 회원으로 등록되어 있지 않다면, **회원 초대** 버튼을 클릭합니다.
- 초대할 회원의 이름, ID, 이메일을 입력한 후 확인 버튼을 클릭합니다.
- 입력된 이메일로 초대 메일이 발송되며, 해당 이메일을 통해 비밀번호를 설정하면 IAM 회원으로 가입이 완료됩니다.
- IAM 회원 초대 기능은 NHN Cloud CONSOLE → 멤버 관리 → IAM 회원 탭에서도 사용할 수 있습니다.

**② 조직관리자 추가**

- 조직관리자를 추가하려면 **조직관리자 추가** 버튼을 클릭합니다.
- 조직관리자 추가 페이지로 이동되며 **상담원 검색** 버튼을 클릭합니다.
- 조직관리자로 추가할 IAM 회원을 검색한 후 선택합니다. 검색 시 이름, 계정, 이메일 중 하나를 입력하여 검색해야 합니다.
- 이후 저장 버튼을 클릭하면 해당 상담원이 조직관리자로 등록됩니다.

## 회사정보 관리
![계약서비스현황_회사정보관리](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-global-management_img0081.png)

PC, 모바일 헬프센터의 푸터 영역에 회사 정보 및 이용약관을 표시하기 위한 정보를 입력하는 메뉴입니다.

**① 추가**

- 회사 정보를 추가하려면 **추가** 버튼을 클릭합니다.
- 입력 페이지로 이동되며 회사 정보, 상표 및 저작권, 이용 약관 정보를 입력한 후 **저장** 버튼을 클릭합니다.

**② 반영**

- 저장한 회사정보는 **[서비스 관리 → 헬프센터 → 구성관리]** 메뉴에서 헬프센터 페이지 푸터에 **반영**할 수 있습니다.

## CTI 관리
CTI 관리 메뉴에서는 Online Contact과 연결할 CTI 정보를 설정하고, 전화 상담을 진행할 상담원의 CTI ID와 CTI 번호를 설정할 수 있습니다.
해당 메뉴는 계약 정보에서 **티켓 관리 → 전화 CTI 사용** 기능을 **사용**으로 설정한 서비스에서만 사용 가능합니다.

### CTI 설정
![계약서비스현황_CTI설정](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-global-management_img0090.png)

Online Contact의 전화 상담 기능과 연결할 CTI 정보를 설정할 수 있습니다.

**① CTI 버전**

- 사용할 CTI 버전을 선택합니다.
- IPCC(Private)는 Private 서비스로, 이용이 필요하다면 Online Contact 고객센터를 통해 **사전 협의**가 필요합니다. ([Online Contact 고객센터 바로가기](https://nhn-contact.oc.nhncloud.com/oc/hc/))
- 모바일 컨택(Mobile Contact)은 NHN Cloud Console에서 **Mobile Contact 서비스를 활성화**한 후 선택할 수 있습니다.

**② 테넌트 ID**

- IPCC 또는 Mobile Contact 관리 담당자로부터 전달받은 **테넌트ID**를 입력합니다.

**③ 테넌트 명칭**

- IPCC 또는 Mobile Contact 관리 담당자로부터 전달받은 **서비스명**을 입력합니다.

**④ 모바일 컨택 활성화**

- 모바일/PC어플리케이션을 통한 전화 상담 서비스로 Online Contact과 연동하여 사용할 수 있습니다. 
- **바로가기** 클릭 시 Mobile Contact 서비스 소개 페이지로 이동됩니다.

**⑤ CTI Log 모니터링**

- 기능을 활성화하면 하루 단위로 CTI 로그가 기록됩니다.
- 기록된 로그는 화면 우측 상단의 계정 이름을 클릭하면 나타나는 **CTI Log 다운로드**를 통해 엑셀 파일로 다운받을 수 있습니다. 

**⑥ 대기 상태 일괄 설정**

- 통화 종료 후 상담원의 대기 상태를 어떻게 변경할 것인지 선택하는 기능입니다.
- **활성화 시** 통화가 종료되면 일괄로 **업무(티켓처리)** 상태로 적용됩니다.
- **비활성화 시** 통화가 종료되면 상태 변경 알림이 표시되어 상담원이 직접 상태를 선택합니다.

**⑦ 아웃바운드 티켓 자동 생성**

- 발신 전화에 대한 **티켓 생성 시점**을 설정할 수 있습니다.
- **활성화 시** 고객과의 연결 성공 여부와 상관없이 자동으로 티켓을 생성합니다.
- **비활성화 시** 고객과 연결되었을 때 자동으로 티켓을 생성합니다.

### CTI 상담원 관리
![계약서비스현황_CTI상담원관리](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-global-management_img0100.png)

전화 상담을 사용할 상담원에게 CTI ID 및 CTI 번호를 등록하는 메뉴입니다.

**① 조회**

- CTI 정보를 입력할 상담원을 검색할 수 있습니다.
- **서비스관리 → 상담원** 메뉴에서 등록된 상담원 중 하나 이상의 서비스에서 전화 권한이 부여되어 있어야 합니다.

**② 수정**

- CTI 정보를 입력하거나 변경하려면 **수정** 버튼을 클릭합니다.

**③ CTI ID, CTI NO**

- CTI ID와 CTI NO를 입력할 수 있도록 컨트롤이 활성화됩니다.
- 상담원의 CTI 정보를 입력한 후 저장 버튼을 클릭하여 반영합니다.
- CTI ID, CTI NO는 상담원 간 중복 입력이 불가합니다.

**④ 전화 위젯**

- CTI 정보를 정상적으로 입력*하였다면, 우측 하단의 **전화 위젯**을 통해 CTI에 로그인할 수 있습니다.

> ※ CTI 정보 취득이 어렵다면 Online Contact 고객센터를 통해 문의 부탁드립니다. 
> ([Online Contact 고객센터 바로가기](https://nhn-contact.oc.nhncloud.com/oc/hc/))

## 권한 변경 로그 관리
![계약서비스현황_권한변경로그관리](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-global-management_img0110.png)

조직 내부 상담원들의 권한을 수정하면 변경된 이력이 저장되며, 해당 내역을 확인할 수 있는 메뉴입니다.

**① 조회**

- 권한 변경 로그 내역을 조회합니다. 
- 조작일시, 조작내용, 이름 등으로 상세하게 검색할 수 있습니다.
- 조회조건에 따라 **서비스, 조작일시, 변경전 권한, 변경후 권한** 등의 정보가 조회됩니다.

## 데이터 이관
![계약서비스현황_데이터이관](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-global-management_img0120.png)

Online Contact으로의 상담 데이터 이관이 필요할 경우, **데이터 이관** 메뉴를 통해 엑셀 파일로 업로드하여 티켓을 일괄로 생성할 수 있습니다.

**① 추가**

- 데이터 이관이 필요하다면 **추가** 버튼을 클릭합니다.

**② 템플릿 다운로드**

- 데이터를 이관할 서비스를 선택한 후, **다운로드** 버튼을 클릭합니다.
- 엑셀 양식 파일이 다운로드되며 선택한 서비스의 현 시점 필드 구성이 반영됩니다.
- 필드 설정은 **서비스관리 → 티켓 → 필드 → 필드관리 탭**에서 설정할 수 있습니다.
- 데이터를 업로드하려면 **다음** 버튼을 클릭합니다.

**③ 데이터 등록** 

- **추가** 버튼을 클릭하여 작성한 엑셀 파일을 선택한 후 **저장** 버튼을 클릭합니다.
- 주의사항을 확인한 후 최종적으로 **확인** 버튼을 클릭하면 엑셀 파일이 정상적으로 업로드됩니다.
- 업로드한 데이터는 예약 상태가 되며, 다음날 오전 1시에 일괄적으로 반영됩니다.

**④ 삭제**

- 예약 상태의 데이터는 **삭제** 버튼을 클릭하여 삭제가 가능합니다.
- 단, 이관이 완료된 데이터는 버튼이 비활성화되어 삭제가 불가합니다.

## My 실적
![계약서비스현황_My실적](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-global-management_img0130.png)

Online Contact 화면 우측 상단에 표시된 **① 계정 이름**을 클릭한 후 **② My 실적**을 선택하면 **③ My 실적 대화상자**가 나타납니다.

해당 화면에서는 **현재 접속 중인 서비스**에서의 티켓, 전화, 채팅 상담에 대한 세부적인 **실시간 누적 데이터**를 확인할 수 있습니다.

상담 유형에 따라 표시되는 세부적인 실적 구분은 다음과 같습니다.

**티켓실적**

- 미할당 
- 처리중 
- 해결
- 완료

**전화실적**

- IB통화(건수/시간)
- OB통화(건수/시간)
- 대기
- 호전환
- 티켓처리
- 채팅처리
- 휴식
- 식사
- 교육
- 취합/보고
- 회의
- 코칭

**채팅실적**

- 대기
- 온라인
- 휴식

## 개인정보설정
![계약서비스현황_개인정보설정](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-global-management_img0140.png)

Online Contact 화면 우측 상단에 표시된 **① 계정 이름**을 클릭한 후 **② 개인정보설정**을 선택하면 **③ 개인정보설정 대화상자**가 나타납니다.

해당 화면에서 Online Contact에 접속하는 사용자의 개인정보설정을 확인하고 변경할 수 있습니다. 

✔ **\[FAQ 바로가기]** [아이디, 이메일, 이름을 변경하거나 삭제하고 싶습니다.](https://nhn-contact.oc.nhncloud.com/oc/hc/article/33/)

✔ **\[FAQ 바로가기]** [비밀번호를 변경하고 싶습니다.](https://nhn-contact.oc.nhncloud.com/oc/hc/article/35/) 

**열람 가능한 정보**

- 계정 
- 이름
- 전화번호
- 이메일
- 언어선택(변경 가능): 서비스 언어 선택과는 별개로 사용자 환경에서의 언어 선택
- 할당(변경 가능): 휴가 등의 사유로 티켓, 채팅 할당을 받지 못하는 경우 상담원 스스로 할당여부 설정 가능