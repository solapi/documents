# 통계 엑셀 파일 다운로드

## Request
```
GET https://api.solapi.com/messages/v4/statistics/excel
```

통계를 엑셀 파일로 만들어 다운로드합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/overview#authorization)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `message:read` | `role-message:read` | `ACTIVE` | `ACTIVE` |  |

### Query Params
| Name | Type | Required | Allowed Operator [[?]](https://docs.solapi.com/api-reference/overview#operator) | Description |
| :--- | :--: | :------: | :--------------: | :---------- |
| startDate | `date` |  | eq | 검색 시작 날짜 |
| endDate | `date` |  | eq | 검색 끝 날짜 |
| subAccountId | `string` |  | eq | 설명 없음 |

---

## Samples

### 통계 엑셀 다운로드

> **Sample Request**

```
http://api.solapi.com/messages/v4/statistics/excel?
```

> **Sample Response**

```json
"PK\u0003\u0004\u0014\u0000\b\u0000\b\u00007)pS\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0013\u0000\u0000\u0000xl/theme/theme1.xml�YM��6\u001a�� xOl�x&3B�\"���n2�`�I��k����H��gƷ\"=.�@�\u000f�R��\u001e\u0016�\u0006h�^��&�Y�f���\u0005IQ\u0016m9�|\u0014Ţ�CbI��~�/I��G\u0017\u0005CgD**x�{W�\u0018\u0011����,��&�+{\u0018)\r<\u0005&8��(�э?\\�H� �`\\E\u0010�\\�2�tT��\u0002�UQ\u0012~Q���\u0005huUȬ�J8�<+Xg����\u0014@9F\u001c\n\u0012�Of3�\u001041\"�\r䥏\u0018)\b���I�<1�I�q���g1j��L�3`1>�<\u0015�\u0013r�1b����\u0018w�\u001f��@�;\u0010y\u001aӛ�\r���y����[N�̦��޸���C=��\u0016�h4\u001a�z\u001e�!�$�{�����ޠ�܄��-\u001a�ݝn��`���n��`0���F5a�w�������\n)\u000e�(;����p�\u001bR\u001c�Qv�)�k���\u0015�����u�I�x�u,A3�n�3����^�3\u001a�\u000eDu\tZE3��Ɗ,ࡐc���2Д#�(�\f\u0012\u0012�!\u0014SI�j��@�Qu/Q���B�\u0012IK\u001d�?��q\u0003����^>�\u0019�|��٣'�\u001e����ϟ=���\u00160o\u0003Ϛ�\u0017?|���>C����\u0017_}�����������\rH�D>���<~��_��ׯ��7%L��\t-�B\u001f�st,\n�m��d*ߐ2Ɂ\u0006\u0014�E�\u001f�f��\u0000��\u0002X+p@�\u0018ޗ����[󇁽'��k��ٝ�\b��B����a�c�5�?��l�~9o\u0002�\u0001�Z�\u000f�\u0007Y\u001e�˜\u0014u�\u0006q\u001a�$0��\u0001א\u0011N42��)!m.>�4��!M�Pb��\u0003�\u0006@�\u00033�Ӡ���۴\u0000\u0006�V�'9\u0004\u0011:��\u0006���~@�B(�\fX�\u0003\u0013hނ���U�\u0004\n�\f�]�y��'\u000b�4�#�%��0�F)Q���\\\u0004&�\u0001F7T�![\u0014M�w@jz�*�.\bф\u001e��a\u000eE�\n>�<o���N�`���n�\u001f��g̵`\u0014���ߧ$��%��=�\u0005V-��<�˶��\"\"(�\u0005�\u0001q�\u0003Q8�\u000b�_9�\u0019�J_\u0010\u001f&�_�nJ��Q��|#��t�\u001f��\u001f\u0011���݇!nF��!���1�7v��1�\u001bú\u0003��ĸ-���\u0017�7�3�؉^0rW�=�\u0012��cʘ;eأh}�+�!sKK\u0007�\u0010�I�4$�����$��ĸ�N����3�J�b�u\u000f�A��(��5��\u001dqw��\u001a,\n��H�����[Kr���\u001d���m#��*����ʞ3os\u001cW��Y\u0013͙\u001d��ͥ�&�>#\r7;\u0010-\u0003�(G`^k�v��\u0005H%�Hj�Q�\u0011�ɲ��ů��*\u0004�O9��e.��Hi��ԛ��q�UЛ�w\u0019F��%l�%S\u001f��l�l�k!>�.wk��xЊ���\u0018��l�`�@\u0019�\u0019\u0003�QR�i���e\u0002�x�\u0013-��~}��Zz����z���zх�_J�\u000f@�.���O �V�sdk����?O�R~;[��z��-\u001d�V\u0012Nf3��\u0006\u001a�l(ݵ\u001f�b��<��s4esy\fi��vX��*\u001dc;\u00000J�����\u0019j+m�b���\u0005V\u000f��9T�ּ4�U��*���]6��@��u�m|2#���\u0014����'��\u0010N�S��\u0004\n\"\u0001�֎��:\u0017��2��X\n�ݴ�B#\u0006�,则�ꦶș���M'ō\u0000����fH�,�:��\u001c�*���׫ֱJ*�D�ZkZ����)9#lb�箙�\u0018�1v��O\r�\\+���o�if6DA_�c�^\u001c\\��6�$����7�?,�T'É�\u001b��O��rg֯�'XR����x{K.��7�q7����ک�\\_��.1X�K�92��8�2aՇ\u001a�VO�1I4b16\u0012�\u0018�\u0018_13�\u0014~}s\u001a㞻Y՚\u0011�j���C�/V����0/կ��\u000evߝu�Vƅ\u001b�7��r�\u0016*\r��M�Ŀ�D\u0010~w�U��@������\u000fJ.\"��_�qNL\u001f�D\u001f�\u0019�Y��N�\u0007d�\u001a�<����\"]��L�\u0005�*LsԲhƏ�\f���>#աq\r�\u000e�[v��LS�5w��L�­\u0018��\u0016㚿u\u0019~�q�\u0005�5߾&l��tm�9�\u001e�(�\u000e�B`~ֱc���x)O6D�o�w�(VM��\f�U\u0014��k��cׁ��>Ʌ�0�\u001f��*]��-�\u001b�\u0003PK\u0007\bv�0�\f\u0007\u0000\u0000\u0019\u001f\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u00007)pS\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u000b\u0000\u0000\u0000_rels/.rels���J�0\u0010\u0006�O\u0011�Mw\u0005\u0011�t/\"�M�>��L��$\u0013��ٷ\u0017\u0004�B]z\u001f���a������-\u0007\u0005��\u0005AA��aT��?��A����@\n.����\u001c_�a�\u001c�dc\u0016ջ�\u0015L��\u0007)���cn8R��\r�<��p\u001aeD=�H�жw2�̀n�)�FA:�=��\u0012iK6\u000f������S(++�r\u0002D�i���:��i~c���\u001d�u�a�����SA�\u0005��D��8R*��/ǰ~N\u001c���5��vв��q�\u0016\n��u\u0012��#��\u001f�\u0000PK\u0007\b�I��\u0000\u0000\u0000K\u0002\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u00007)pS\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0018\u0000\u0000\u0000xl/worksheets/sheet1.xml�VAo�6\u0018�+\u0004Oޡ����lH*R;i��I`��`h�&*�\u0002I�Ύ�W\fm\u000e=��\u0001i�\u0002Y�C\u000ek�\u0002\u00190`�'��� )�*[6�� >����}�?�w��\u0003GT*&|\u0007�E\u0003\u0002�\u0013�e~߁�:۷~�@i�w�'|��c��]�\u001e\t�T\r(�`�=_9p�uPEH�\u0001�X\u0015E@�1�zBr�UQ�>R�������,�(#��\u000fS���\u001e\u000f��1B�\f9�uj\"��5\u0013�\u001a�@��8�\u001e;���ap�\b\u001e`�\u000e���qb\n\u0001'�ݾ/$>��\u0003��\u0006&3�d�d�\u0019�B��.\u0012�Q\u001at��+��0����a;)ρ\u0004]��CO��h���@;�,A ��c>m�#��ȁF\u0016�\t/��@��q�*B}��R\t\"�&�S�\u0015p\u0016�\u0016\u0002��\u000e܀`ĺz�@ˀ�\f�\u0016�q\n�7�TP�\u0011�Qf��Z�Y�I�s���MP\u001a.�B\u001dk��R��LR�\u0000�o�Y�햞�(Z%��$&o�\u0010h\u0007*-�k\u001f��������\\\u001b�\u001bʽ,%z?��\\��������ϗYr-KNY �|����\u0012��O~y6=��D�Z ��\u0014^\\�\u0017WѻW��n�X��vV\u0018���\u001bac������Et>���\\#�Y\u0010�9\t?�=}�\u0001\u00146;�+s�.��:��z��jkT\u000fV��$.(�:�+�|�\u0015�����e�e\u0002�\u0017g����\u0017W J�\u0017�ګ�7�.�Z\u001b���j�'�:�\\6�v)6Xש�\u001c�L�b�u\u001d�_6��r:}}\u0012~�\u0007\u0014bu砱��\u0007Y���e������i���ʭ\u001e�b4?�\u0016\u0004���Z�ck\u0019��L\u0013���i�g%���Ek�h=E�,w+E�,�����Ewr��\\�A�.dx��6r\u001d���^.���\u001e��\u0019�.�o�h\u0003ܧM,��W��=�@�x\u0007\u0002�Ν�^� AK\u0010\u001c\n�\u0005��\u0006\u0014w��W�!�\t�g\u000b�ڱo��a\u0000�d���Pv` ���i\b\u0006B�����W\u000f�\u00037��F�|Ǫ�`�\u0001�\u0019��A\u0011\u001c�_�0 �1�\u0011�I�.��2�\\h�U��\u000bPK\u0007\b�n\u0013Bh\u0003\u0000\u0000�\b\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u00007)pS\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0013\u0000\u0000\u0000[Content_Types].xml���n� \u0010��>��Z\u0019�\u000eUU��дc�!}\u0000\ng\u001b\u00058�\u0011�y��$�\u0010���f�������0[��\u0016\u001dD2�+6�\u0013V�W��o*��~+�XAIz--z��\u001e�-�w��>\u0000\u0015���*֦\u0014�� Ղ��1�1:��clD�j#\u001b\u0010\u000f�ɣP�\u0013�T�A��gK��֦�O�\u000fF\"Xb�ˡp`UL�`��ɠ\u0017��g��H�\u0011l���\u0004��eb�0��\u000e8��� F��Xɘޥ���ފ\u001d��\u0017�_\u0016\u0019q�um\u0014hT[\u0007>q\n\u0011��\u0016 9��Ν4���\u0002?\u0017�����F����\u0015\u001f�\u0005\u0007\"����e�\u0000)�-Ѝ�=���#a�.F���;g�Q�o�,��T�ZE\f$\u0014F�{{��\u000f��\u00101@L\u0006~��(C�;�,�0<\\\rz�-�G1�\u0006PK\u0007\b��1�X\u0001\u0000\u0000h\u0004\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u00007)pS\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0010\u0000\u0000\u0000docProps/app.xml�����0\u0010��<E���I)+�r�B-h\u000f *��\u001c�q&���ǲg���\u0004\u0012o�\u00047ފ>\u0004JB�-��m�߿?�F\\��M\u001a\bѠ�Y6IY\u0002Nca�6g��7\u0017/Y\u0012I�BYt��\u000e\"����*��@\u0006b���ŜUD~�y�\u0015�*NЃkk[b�\u0015�\t�-ǲ4\u001a��\u001fjpħizɡ%p\u0005\u0014\u0017�)�����7�@��ŻM�!2)^yo�Vd��wF\u0007�XR��`\u0005?\u001e�%�5�`����ǭXkea\u0011��R�\b�\u001f\u0004q\u0003���J�\u0010�hhހ&\fI4�!gS�|R\u0011z��5*\u0018刍��\u0019j�#\u0005�\u0001�}�\u0000(\n��|\u0014���ówf&��`f���\u0007� R�Sč!\u000b�}�R��A�\u001d\u0013\u000f\f#{��������ݗ\u001f\u001f����E6�:�\u001d6 \u0005��\u0005�^�N\n�T�5�>��\r.\u0015�~���XW*@�D��\u001f\u0004q�y\b�\u000fYT�m��{�\u0007�-܍�.��I�<M�\u0013�k�\u001fN[�\u0006PK\u0007\b�A9��\u0001\u0000\u0000\u001f\u0003\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u00007)pS\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0011\u0000\u0000\u0000docProps/core.xml���N�0\u0010E�|E�}b;�\u0002Q�J<�@TB�\b�β���_�\rI�\u001e%iӢv�v�3wFS�Z��\u001f�AZS!�\u0011���VH����r�ޠ$Df\u0004S�@��\u0010Ь�(�+����\u0003\u001f%���ʄ��\nmbt\u0005Ɓo@��Y\u0007��je�f1d֯�c���\u0001�L���\u0004�\fw�ԍD�C\n>\"ݷW=@p\f\n4�\u00180�(>x#x\u001d�6�ʑS˸up�*� ��6���4M�L�\u00189!\u0014,�_�USi�Sq@u)x�=�h}��rPO�%>�u�S,ą\u0015r%A�m\u000f�S�\u0014�\u000f? A$m��\u0010~��O�\u001f�sT�$�)�)�.�UAn����n��.�Pл��&�\u0001u�O^��\u0005PK\u0007\b{1�{2\u0001\u0000\u0000^\u0002\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u00007)pS\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\r\u0000\u0000\u0000xl/styles.xml�T�o� \u0010~�_�xw\u0000���ȸZ�Z��M��I}%6NP�a\u0001�M��'�8NTi��'�����8��NI�ʭ\u0013FSHf\u0018\u0002�+S\u000b���ۦ��\u00108�tͤќ�#w���;��iϹ\u0007���Q���]\"�=W��L�u�dc�b�͌�!�Z�j\u0017��D1�\u0019RLh80,U�/$�ٗC\u001bUF�̋���\u001f{.\bT�|�ic�Vr\n;��\nt$�񘡇�$Q��ƙ��*��i\u001aQ�Z\u0017h�X51e6~\u001f\u0013I\u0011���1�;��Z�h�]�\u0001��@P����\u001a���2�X��\\�\u0000�\"o�\u0012�\b^��0\u000e@�|\u0000������\u0001 }�f��pǤ�Z\u0011\\P�qZ\\�7BJ7\n��\u0000!e���{nu)�\u0004'{sl9��h>��~��Yv$qz\u0011���E�5����9�>@E.y�Q�[�ۇ՛\u0016�C�BE^\u000b�3��P�\u0018q2\\�W\\ʧ�^��+�\u0001��J�\u001fj\n1\u0004�\u0012FSHy2\u0007�a\u0013�/�\u0006���\u0005]s���\\ʾ\u0012}N\u000fB')�\u0012\u0006L�3\u0005�\u001e��B_\u0013��\"���\np�\u000f�2��\r�\u0010Լa\u0007�7�C\n'�3��A�g���������~\f�\"Y��;��|���\u0015\u0014��_}\\���8���<Jnx\u001a-��:J���z].p��~M���o�p����)�$K'E����S�O\u0013F��f�߿Q�]i_�\u0019��\u0012\u001c�7�DI���<�I�2%�:KV�i�^hOߧ�`D�$>]z��\u0014z��ءK�P�\u000fE��\u0013h����PK\u0007\b�b�ύ\u0002\u0000\u0000\u0003\u0006\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u00007)pS\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u001a\u0000\u0000\u0000xl/_rels/workbook.xml.rels���j�0\f��{\n��⤃1F�^Ơב=�q�8Զ�����\u000f2hW(c�^\u0004�\u0004�����9\u0006u��\u0013%\u0003MU��䨟�h�{|\u0001�bSo\u0003%4� î}�~`�2Qb?eVs\f�\rx���5;��rE\u0019�\u001c�@%Z�ʨ�u\u0007;�����.�;���T��@��\r�n���n\u001a���\u001b���In 4�\u0012�Au��(\u0006~r5�\u0000�6~sO�x�x��Q������\u000e'*\u0007��r�8�X�����zr�\rPK\u0007\bN�n:�\u0000\u0000\u0000,\u0002\u0000\u0000PK\u0003\u0004\u0014\u0000\b\u0000\b\u00007)pS\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u000f\u0000\u0000\u0000xl/workbook.xml���n\u001b!\u0010\u0000�{�\u0002�=fq⤶�#Um%_*\u001f�^+\f�^d`\u0010�������?����W�GD�ۭT�\u0013\u0002ě\u0019f���w�)[\n\u0012Ĭ\u0002�A��� ���ǫ��rQ�(G\u0001%�1�������qOtd�w!KhJ�+γnЫ<�����U�3J\u0007�cBer�X����^�\u0000��J�1������[���HB����\u001b\u001b�y�\u001aΫtl�&\u001fU�{�l9\u000f(0�W�C���\u000e%tb1ɝX���Չ2�e���1�\u0017���\u000b1��Y����י���}\u0014\u0007̩\\>\u0018[�HX\u0000s��\u001d�6�k�3\u0012���5�ͿN�\u00123X�֕�\u0006��K\u0010�7�\u0010�j�\n�]�'��\u0012D�v�F���a�5�\u001d\u000bCF�����?�<��|��U̗�Y\u000e\u0003QP��f�w\b,�����fH�O�VN�\u0012�A�\u0013���\u000f˧��<\u0003PK\u0007\b�?�~\u0001\u0000\u0000�\u0002\u0000\u0000PK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u00007)pSv�0�\f\u0007\u0000\u0000\u0019\u001f\u0000\u0000\u0013\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000��\u0000\u0000\u0000\u0000xl/theme/theme1.xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u00007)pS�I��\u0000\u0000\u0000K\u0002\u0000\u0000\u000b\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000��M\u0007\u0000\u0000_rels/.relsPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u00007)pS�n\u0013Bh\u0003\u0000\u0000�\b\u0000\u0000\u0018\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000��q\b\u0000\u0000xl/worksheets/sheet1.xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u00007)pS��1�X\u0001\u0000\u0000h\u0004\u0000\u0000\u0013\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000��\u001f\f\u0000\u0000[Content_Types].xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u00007)pS�A9��\u0001\u0000\u0000\u001f\u0003\u0000\u0000\u0010\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\r\u0000\u0000docProps/app.xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u00007)pS{1�{2\u0001\u0000\u0000^\u0002\u0000\u0000\u0011\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\u000f\u0000\u0000docProps/core.xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u00007)pS�b�ύ\u0002\u0000\u0000\u0003\u0006\u0000\u0000\r\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000��\t\u0011\u0000\u0000xl/styles.xmlPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u00007)pSN�n:�\u0000\u0000\u0000,\u0002\u0000\u0000\u001a\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\u0013\u0000\u0000xl/_rels/workbook.xml.relsPK\u0001\u0002-\u0003\u0014\u0000\b\u0000\b\u00007)pS�?�~\u0001\u0000\u0000�\u0002\u0000\u0000\u000f\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000 \u0000���\u0014\u0000\u0000xl/workbook.xmlPK\u0005\u0006\u0000\u0000\u0000\u0000\t\u0000\t\u0000>\u0002\u0000\u0000�\u0016\u0000\u0000\u0000\u0000"
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
  url: 'http://api.solapi.com/messages/v4/statistics/excel?'
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
$url = "http://api.solapi.com/messages/v4/statistics/excel?";

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

url = "http://api.solapi.com/messages/v4/statistics/excel?"
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
	http://api.solapi.com/messages/v4/statistics/excel?
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/statistics/excel?")

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
  uri := "http://api.solapi.com/messages/v4/statistics/excel?"

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
    String targetUrl = "http://api.solapi.com/messages/v4/statistics/excel?";

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

