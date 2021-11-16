# 메시지 목록 엑셀다운로드

## Request
```
GET https://api.solapi.com/messages/v4/list/excel
```

메시지의 목록을 다운로드합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/overview#authorization)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `message:read` | `role-message:read` | `ACTIVE` | `ACTIVE` |  |

### Query Params
| Name | Type | Required | Allowed Operator [[?]](https://docs.solapi.com/api-reference/overview#operator) | Description |
| :--- | :--: | :------: | :--------------: | :---------- |
| criteria | `string` |  | eq | 검색 조건에 사용되는 필드명<br>criteria 의 값은 'key1,key2,key3' 과 같이 ,(콤마) 로 구분되며 cond, value 와 함께 사용됩니다.<br>- messageId - 메시지 아이디 입니다.<br>- groupId - 그룹 아이디 입니다.<br>- to - 수신 번호 입니다.<br>- from - 발신 번호 입니다.<br>- type - 문자 메시지의 타입 입니다.  (SMS, LMS, MMS, ATA, CTA, CTI)<br>- dateCreated - 그룹 생성일 입니다.<br>- dateUpdated - 그룹 정보를 변경한 마지막 시각 입니다.<br>- replacement - 대체 발송 여부 입니다. (true, false)<br>- statusCode - 문자 메시지의 상태 코드 입니다. |
| cond | `string` |  | eq | 검색 조건에 사용되는 연산자<br>criteria 와 같이 'cond1,cond2' 와 같이 ,(콤마)로 구분되며, criteria,value 와 함께 사용됩니다.<br>- eq - 같음 (=)<br>- ne - 같지 않음 (!=)<br>- gt - 보다 큼 (>)<br>- gte - 보다 크거나 같음 (>=)<br>- lt - 보다 작음 (<)<br>- lte - 보다 작거나 같음 (<=) |
| value | `string` |  | eq | 검색 값<br>criteria , cond 값에 대응하는 value 입니다.<br>criteria='messageId,statusCode'<br>cond='eq,eq'<br>일 경우 groupId 에 대응하는 value 값을 찾고 status 에 대응하는 값을 찾는 조건 입니다.<br>e.g - value='메시지아이디,2000' |
| subAccountId | `string` |  | eq | 설명 없음 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |
| dateType | `string` |  | eq | 설명 없음 |
| startDate | `date` |  | eq | 검색 시작 날짜 |
| endDate | `date` |  | eq | 검색 끝 날짜 |

---

## Samples

### 발송내역 엑셀 다운로드

> **Sample Request**

```
http://api.solapi.com/messages/v4/list/excel?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq
```

> **Sample Response**

```json
"PK\u0003\u0004\u0014\u0000\b\u0000\b\u00004)pS\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0013\u0000\u0000\u0000xl/theme/theme1.xml�YM��6\u001a�� xOl�x&3B�\"���n2�`�I��k����H��gƷ\"=.�@�\u000f�R��\u001e\u0016�\u0006h�^��&�Y�f���\u0005IQ\u0016m9�|\u0014Ţ�CbI��~�/I��G\u0017\u0005CgD**x�{W�\u0018\u0011����,��&�+{\u0018)\r<\u0005&8��(�э?\\�H� �`\\E\u0010�\\�2�tT��\u0002�UQ\u0012~Q���\u0005huUȬ�J8�<+Xg����\u0014@9F\u001c\n\u0012�Of3�\u001041\"�\r䥏\u0018)\b���I�<1�I�q���g1j��L�3`1>�<\u0015�\u0013r�1b����\u0018w�\u001f��@�;\u0010y\u001aӛ�\r���y����[N�̦��޸���C=��\u0016�h4\u001a�z\u001e�!�$�{�����ޠ�܄��-\u001a�ݝn��`���n��`0���F5a�w�������\n)\u000e�(;����p�\u001bR\u001c�Qv�)�k���\u0015�����u�I�x�u,A3�n�3����^�3\u001a�\u000eDu\tZE3��Ɗ,ࡐc���2Д#�(�\f\u0012\u0012�!\u0014SI�j��@�Qu/Q���B�\u0012IK\u001d�?��q\u0003����^>�\u0019�|��٣'�\u001e����ϟ=���\u00160o\u0003Ϛ�\u0017?|���>C����\u0017_}�����������\rH�D>���<~��_��ׯ��7%L��\t-�B\u001f�st,\n�m��d*ߐ2Ɂ\u0006\u0014�E�\u001f�f��\u0000��\u0002X+p@�\u0018ޗ����[󇁽'��k��ٝ�\b��B����a�c�5�?��l�~9o\u0002�\u0001�Z�\u000f�\u0007Y\u001e�˜\u0014u�\u0006q\u001a�$0��\u0001א\u0011N42��)!m.>�4��!M�Pb��\u0003�\u0006@�\u00033�Ӡ���۴\u0000\u0006�V�'9\u0004\u0011:��\u0006���~@�B(�\fX�\u0003\u0013hނ���U�\u0004\n�\f�]�y��'\u000b�4�#�%��0�F)Q���\\\u0004&�\u0001F7T�![\u0014M�w@jz�*�.\bф\u001e��a\u000eE�\n>�<o���N�`���n�\u001f��g̵`\u0014���ߧ$��%��=�\u0005V-��<�˶��\"\"(�\u0005�\u0001q�\u0003Q8�\u000b�_9�\u0019�J_\u0010\u001f&�_�nJ��Q��|#��t�\u001f��\u001f\u0011���݇!nF��!���1�7v��1�\u001bú\u0003��ĸ-���\u0017�7�3�؉^0rW�=�\u0012��cʘ;eأh}�+�!sKK\u0007�\u0010�I�4$�����$��ĸ�N����3�J�b�u\u000f�A��(��5��\u001dqw��\u001a,\n��H�����[Kr���\u001d���m#��*����ʞ3os\u001cW��Y\u0013͙\u001d��ͥ�&�>#\r7;\u0010-\u0003�(G`^k�v��\u0005H%�Hj�Q�\u0011�ɲ��ů��*\u0004�O9��e.��Hi��ԛ��q�UЛ�w\u0019F��%l�%S\u001f��l�l�k!>�.wk��xЊ���\u0018��l�`�@\u0019�\u0019\u0003�QR�i���e\u0002�x�\u0013-��~}��Zz����z���zх�_J�\u000f@�.���O �V�sdk����?O�R~;[��z��-\u001d�V\u0012Nf3��\u0006\u001a�l(ݵ\u001f�b��<��s4esy\fi��vX��*\u001dc;\u00000J�����\u0019j+m�b���\u0005V\u000f��9T�ּ4�U��*���]6��@��u�m|2#���\u0014����'��\u0010N�S��\u0004\n\"\u0001�֎��:\u0017��2��X\n�ݴ�B#\u0006�,则�ꦶș���M'ō\u0000����fH�,�:��\u001c�*���׫ֱJ*�D�ZkZ����)9#lb�箙�\u0018�1v��O\r�\\+���o�if6DA_�c�^\u001c\\��6�$����7�?,�T'É�\u001b��O��rg֯�'XR����x{K.��7�q7����ک�\\_��.1X�K�92��8�2aՇ\u001a�VO�1I4b16\u0012�\u0018�\u0018_13�\u0014~}s\u001a㞻Y՚\u0011�j���C�/V����0/կ��\u000evߝu�Vƅ\u001b�7��r�\u0016*\r��M�Ŀ�D\u0010~w�U��@������\u000fJ.\"��_�qNL\u001f�D\u001f�\u0019�Y��N�\u0007d�\u001a�<����\"]��L�\u0005�*LsԲhƏ�\f���>#աq\r�\u000e�[v��LS�5w��L�­\u0018��\u0016㚿u\u0019~�q�\u0005�5߾&l��tm�9�\u001e�(�\u000e�B`~ֱc���x)O6D�o�w�(VM��\f�U\u0014��k��cׁ��>Ʌ�0�\u001f��*]��-�\u001b�\u0003PK\u0007\bv�0�\f\u0007\u0000\u0000\u0019\u001f\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u00004)pS\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u000b\u0000\u0000\u0000_rels/.rels���J�0\u0010\u0006�O\u0011�Mw\u0005\u0011�t/\"�M�>��L��$\u0013��ٷ\u0017\u0004�B]z\u001f���a������-\u0007\u0005��\u0005AA��aT��?��A����@\n.����\u001c_�a�\u001c�dc\u0016ջ�\u0015L��\u0007)���cn8R��\r�<��p\u001aeD=�H�жw2�̀n�)�FA:�=��\u0012iK6\u000f������S(++�r\u0002D�i���:��i~c���\u001d�u�a�����SA�\u0005��D��8R*��/ǰ~N\u001c���5��vв��q�\u0016\n��u\u0012��#��\u001f�\u0000PK\u0007\b�I��\u0000\u0000\u0000K\u0002\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u00004)pS\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0018\u0000\u0000\u0000xl/worksheets/sheet1.xml��Mo�6\u0018ǿ\n�{-R/vdH*�I�5]�f/ٍ�i��$\n$\u001d;;uK\n\u0004�i@\n\u0014�3\u0018�a�N�\u001al\u001d�O\u0014)�a�,\u000be�z�\u000f�I�~=�c���i\u001c�C*$�\u000fq\u0003A@���Y2��{\u001b\u000f� ��$}\u0012����J�0�&\\��#J\u0015��Q\"}8R*m\u001b�\fG4&��S�L�h�EL�lp14d*(�R\u001c\u0019&BM#&,�����O\u0006\u001f\fXH�<\u001c�4Q�\u0010A#�\u0018O䈥r�\u0016�����x1N\u001f�<N�b\u0007,b�\f� \u000e۽a�\u00059��\u000f��&�2�\u001c܊�Y(��\u0003�\byl,\n�}Ϯ�\u001a$��W��F�<�\u0002�逌#��O�(\u001b��\u000f�\u0003\u0001\u001f��%�\t=��3>�!���yTΕ\u0005��G]*C�(\u001f:\u000e4\u0002/�,�Å�B\u0010�i�9a}5�!nB\u0010������D�-\u0004�\u0012,\b*��W\nv%8����B�\u0012��`��B�\u0012Z�`�\u0016�*a�\u0016��\u0017p+\u001e�Z��+�z]q��}\u0017Ƣ!e�D��\u0013|\u0002D�\u0011���)��\"�V?Q�t`��\u0005�\bC�|(���w\u0018\\�;���ջy>�g�^�y�\u0019��g�\u0015�����y~6�{\t��'��ev~���:�����>\u0005wu8�c���Y�c\u001d�O�|\u0002ܸ\u0001�g��o�\n7u$��2��\u0006��#��/�_^�)=\u001d��?\u0016E]|��f:�}\u0003,K�\u000b��\u0006x����\f�\u000b^�\u001a�O�ޛ\u0010��ޛZ��\u000e��:���tth���Dx\rY��1B�������t���~�m��uy]�7?���Z�-kw���ov�no�۽�u���\b��K�\u001eߓ��9E�J\u000f�选L��:\u0001\u0018�?�\u0003��/>\u0000l�g3�f�\u0000��/O�E\u0017���Ɣ\f�\u000e\u0011C�H\u0010с�!j� \u0010�\r���xZ�:\u0010\u001cp�x�\u001c�(�SQ�,\b\u0006����\b�\"�9U�\u0014p�h���ʇ)\u0017J\u0010� \u0018q���\"Q7e>�M�v�-�u`q2+\u0016��\fIq0a� \u00180���-|1�ϑbK7��:�\u0017PK\u0007\b�%\u0001�X\u0003\u0000\u0000�\u0007\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u00004)pS\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0013\u0000\u0000\u0000[Content_Types].xml���n� \u0010��>��Z\u0019�\u000eUU��дc�!}\u0000\ng\u001b\u00058�\u0011�y��$�\u0010���f�������0[��\u0016\u001dD2�+6�\u0013V�W��o*��~+�XAIz--z��\u001e�-�w��>\u0000\u0015���*֦\u0014�� Ղ��1�1:��clD�j#\u001b\u0010\u000f�ɣP�\u0013�T�A��gK��֦�O�\u000fF\"Xb�ˡp`UL�`��ɠ\u0017��g��H�\u0011l���\u0004��eb�0��\u000e8��� F��Xɘޥ���ފ\u001d��\u0017�_\u0016\u0019q�um\u0014hT[\u0007>q\n\u0011��\u0016 9��Ν4���\u0002?\u0017�����F����\u0015\u001f�\u0005\u0007\"����e�\u0000)�-Ѝ�=���#a�.F���;g�Q�o�,��T�ZE\f$\u0014F�{{��\u000f��\u00101@L\u0006~��(C�;�,�0<\\\rz�-�G1�\u0006PK\u0007\b��1�X\u0001\u0000\u0000h\u0004\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u00004)pS\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0010\u0000\u0000\u0000docProps/app.xml���n\u00131\u0010��<���ƛRU(�B\t�\u0007\u0010������&V�\u001e�3]m8!�\\��pG=p㭚�@�K��p�6�����񨫶�Y\u0003�\u001c�B�G�� X,]X\u0015�f���ȈM(��\u0000��\u0000�+�L�\u0013FH쀲���\n�f�\u0013)ɮ�64�\b��}��6L#L+�U�,����\u0010X������!�P��'C18N\u001a�_�\u0012m�G��M\u0004\u0012Z���;k�a�o�MHXq�����<,�\u0019�\u0005���x�s%\u000fS����4aԕ�\u0004J�\u0005u\r���ܸDZ5<i�2���G(Ĺ�>\u0018�\u000e�\u0010�I�\u0004\u0016Cې����I��tGk\u0000&%\u001b�\fb\u001f�9xr�]�q��.�qcg0�h%�\u0011��=лjn\u0012��x|H�3\f�\u0003�������\u001f�\u001e?��~�y\u0002ڿ]+��%S��\t\u001b��S�ƅ;��K�\u0019��\\�E�X�\u0004�\f���\u0017��&B��tm�\n�]�i�ۂ�a���r�?����w����ֿ\u0001PK\u0007\b\u0010%�\u0001\u0000\u0000\u0019\u0003\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u00004)pS\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0011\u0000\u0000\u0000docProps/core.xml���N�0\u0010E�|E�}b;�\n�$�xt����\"\u0010;˞�\u0016~�6$�{��M��\u0015۹w��\u0019M9k�J~�\u0007iM�hFP\u0002�[!ͦBo�yz��\u0010�\u0011LY\u0003\u0015�A@������ë�\u000e|�\u0010�V+\u0013\n�*���\u0015\u0018\u0007�\u0005�Bf\u001d�V����ŐY����/�\u0001�\u00132�\u001a\"\u0013,2�\u0001S7\u0012�\u001e)��t�^�\u0000�1(�`b�4����u���+'N-���E���8�� Gc�4Y3�c�P��xY����t���R��{`����堞�%>�u�S,ą\u0015r-A�s�\u0014�\u000f? A$m��\u0010���O\u001e\u001eWsT�$�)�)���MA�k��M����\u001b\nz?���\u0003�.��KԿPK\u0007\b��q=1\u0001\u0000\u0000^\u0002\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u00004)pS\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\r\u0000\u0000\u0000xl/styles.xml�T�o� \u0010~�_�xw\u0000���ȸZ�Z��M��I}%6NP�a\u0001�M��'�8NTi��'�����8��NI�ʭ\u0013FSHf\u0018\u0002�+S\u000b���ۦ��\u00108�tͤќ�#w���;��iϹ\u0007���Q���]\"�=W��L�u�dc�b�͌�!�Z�j\u0017��D1�\u0019RLh80,U�/$�ٗC\u001bUF�̋���\u001f{.\bT�|�ic�Vr\n;��\nt$�񘡇�$Q��ƙ��*��i\u001aQ�Z\u0017h�X51e6~\u001f\u0013I\u0011���1�;��Z�h�]�\u0001��@P����\u001a���2�X��\\�\u0000�\"o�\u0012�\b^��0\u000e@�|\u0000������\u0001 }�f��pǤ�Z\u0011\\P�qZ\\�7BJ7\n��\u0000!e���{nu)�\u0004'{sl9��h>��~��Yv$qz\u0011���E�5����9�>@E.y�Q�[�ۇ՛\u0016�C�BE^\u000b�3��P�\u0018q2\\�W\\ʧ�^��+�\u0001��J�\u001fj\n1\u0004�\u0012FSHy2\u0007�a\u0013�/�\u0006���\u0005]s���\\ʾ\u0012}N\u000fB')�\u0012\u0006L�3\u0005�\u001e��B_\u0013��\"���\np�\u000f�2��\r�\u0010Լa\u0007�7�C\n'�3��A�g���������~\f�\"Y��;��|���\u0015\u0014��_}\\���8���<Jnx\u001a-��:J���z].p��~M���o�p����)�$K'E����S�O\u0013F��f�߿Q�]i_�\u0019��\u0012\u001c�7�DI���<�I�2%�:KV�i�^hOߧ�`D�$>]z��\u0014z��ءK�P�\u000fE��\u0013h����PK\u0007\b�b�ύ\u0002\u0000\u0000\u0003\u0006\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u00004)pS\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u001a\u0000\u0000\u0000xl/_rels/workbook.xml.rels���j�0\f��{\n��⤃1F�^Ơב=�q�8Զ�����\u000f2hW(c�^\u0004�\u0004�����9\u0006u��\u0013%\u0003MU��䨟�h�{|\u0001�bSo\u0003%4� î}�~`�2Qb?eVs\f�\rx���5;��rE\u0019�\u001c�@%Z�ʨ�u\u0007;�����.�;���T��@��\r�n���n\u001a���\u001b���In 4�\u0012�Au��(\u0006~r5�\u0000�6~sO�x�x��Q������\u000e'*\u0007��r�8�X�����zr�\rPK\u0007\bN�n:�\u0000\u0000\u0000,\u0002\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u00004)pS\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u000f\u0000\u0000\u0000xl/workbook.xml�ұn�0\u0010\u0000н_A�\u001eSL�5L\u0007(�\u0000^\n\u000fiw�<Y�I\u001eAR��\u0015Y�\u0016�ҽ��-\u0015D!�*Pd�D�\u0004���ny�y�\u000e��� A�*`\u00184\u0019\u001bv\u0012>�ݞ�\u0003��\nF9\n(�\u0019�Wo����[�=�\u000bYBSJ\\p�u�^�\u0019E\f�w5%�J�Q��\u001c\u0013*�\u001b��\u001d?��K�\r0\n��\u001a���j�H��\u0018ʈ$t�X\n��1O�ׯ�J�6�i�Q\u0015��Ζ�\u0002�z��\u0005Jj�PB'�܉�\u000b�[�(S]f�<\u001f�|Q���\u0010cɫem\u001d~\u0019��\u0018?)�Gq�����؂F�\u001c��{�� ��Ck������\u0000��׉Mb\u0006kպrנ�t\t��m%\u0004�ں�i��A�\u0004ѿ\u001d����lحM���o��\u001f��_�\u001f�N�\u000f�PP��f�u\b,-����fH�O�VNo\u0012���\u0012��U\u001f�Os��\u0003PK\u0007\b,�Ch{\u0001\u0000\u0000z\u0002\u0000\u0000PK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u00004)pSv�0�\f\u0007\u0000\u0000\u0019\u001f\u0000\u0000\u0013\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000��\u0000\u0000\u0000\u0000xl/theme/theme1.xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u00004)pS�I��\u0000\u0000\u0000K\u0002\u0000\u0000\u000b\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000��M\u0007\u0000\u0000_rels/.relsPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u00004)pS�%\u0001�X\u0003\u0000\u0000�\u0007\u0000\u0000\u0018\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000��q\b\u0000\u0000xl/worksheets/sheet1.xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u00004)pS��1�X\u0001\u0000\u0000h\u0004\u0000\u0000\u0013\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000��\u000f\f\u0000\u0000[Content_Types].xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u00004)pS\u0010%�\u0001\u0000\u0000\u0019\u0003\u0000\u0000\u0010\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\r\u0000\u0000docProps/app.xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u00004)pS��q=1\u0001\u0000\u0000^\u0002\u0000\u0000\u0011\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\u000f\u0000\u0000docProps/core.xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u00004)pS�b�ύ\u0002\u0000\u0000\u0003\u0006\u0000\u0000\r\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\u0010\u0000\u0000xl/styles.xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u00004)pSN�n:�\u0000\u0000\u0000,\u0002\u0000\u0000\u001a\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\u0013\u0000\u0000xl/_rels/workbook.xml.relsPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u00004)pS,�Ch{\u0001\u0000\u0000z\u0002\u0000\u0000\u000f\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\u0014\u0000\u0000xl/workbook.xmlPK\u0005\u0006\u0000\u0000\u0000\u0000\t\u0000\t\u0000>\u0002\u0000\u0000�\u0016\u0000\u0000\u0000\u0000"
```

> **Sample Code**

{% tabs %}

{% tab title="NODE" %}

```javascript
var request = require('request');

var options = {
  headers: {
    Authorization:
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4'
  },
  method: 'GET',
  json: true,
  url:
    'http://api.solapi.com/messages/v4/list/excel?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq'
};

request(options, function(error, response, body) {
  if (error) throw error;
  console.log('result :', body);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/list/excel?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq";

$options = array(
    'http' => array(
        'header'  => "Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4\r\n",
        'method'  => 'GET'
    )
);

$context  = stream_context_create($options);
$result = file_get_contents($url, false, $context);

var_dump($result);

```
{% endtab %}

{% tab title="PYTHON" %}

```python
import requests

url = "http://api.solapi.com/messages/v4/list/excel?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4"
}

response = requests.get(url, headers=headers)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X GET \
	-H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
	http://api.solapi.com/messages/v4/list/excel?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/list/excel?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4"
}
http = Net::HTTP.new(uri.host, uri.port)
request = Net::HTTP::Get.new(uri.request_uri, headers)

response = http.request(request)
puts response.code
puts response.body

```
{% endtab %}

{% tab title="GO" %}

```go
package main

import (
  "fmt"
  "io/ioutil"
  "net/http"
  "strings"
)

func main() {
  uri := "http://api.solapi.com/messages/v4/list/excel?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq"

  req, err := http.NewRequest("GET", uri, nil)
  if err != nil { panic(err) }

  req.Header.Set("Authorization", "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4")

  client := &http.Client{}
  resp, err := client.Do(req)
  if err != nil { panic(err) }
  defer resp.Body.Close()

  bytes, _ := ioutil.ReadAll(resp.Body)
  str := string(bytes)
  fmt.Println(str)
}

```
{% endtab %}

{% tab title="JAVA" %}

```java
package solapi;

import java.io.BufferedReader;
import java.io.DataOutputStream;
import java.io.InputStreamReader;
import java.net.HttpURLConnection;
import java.net.URL;

public class Request {
  public static void main(String[] args) throws Exception {
    String targetUrl = "http://api.solapi.com/messages/v4/list/excel?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("GET");

    con.setRequestProperty("Authorization", "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4");

    con.setDoOutput(true);
    DataOutputStream wr = new DataOutputStream(con.getOutputStream());
    wr.writeBytes(parameters);
    wr.flush();
    wr.close();

    int responseCode = con.getResponseCode();
    BufferedReader in = new BufferedReader(new InputStreamReader(con.getInputStream()));
    String line;
    StringBuffer response = new StringBuffer();
    while ((line = in.readLine()) != null) {
      response.append(line);
    }
    in.close();

    System.out.println("HTTP response code : " + responseCode);
    System.out.println("HTTP body : " + response.toString());
  }
}

```
{% endtab %}

{% endtabs %}

---

> 문서 생성일 : 2021-11-16

