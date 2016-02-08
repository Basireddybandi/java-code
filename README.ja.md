���\�[�X�T�[�o�[����
====================

�T�v
----

����̓��\�[�X�T�[�o�[�� Java �ɂ������ł��B [OpenID Connect Core 1.0][2]
�Œ�`����Ă���[���[�U�[���G���h�|�C���g][1] ���T�|�[�g���A�܂��A[RFC 6750][3]
(The OAuth 2.0 Authorization Framework: Bearer Token Usage)
�ɒ�`����Ă�����@�ŃA�N�Z�X�g�[�N�����󂯎��ی샊�\�[�X�G���h�|�C���g�̗���܂�ł��܂��B

���̎����� JAX-RS 2.0 API �� [authlete-java-jaxrs][4] ���C�u������p���ď�����Ă��܂��B
JAX-RS �� _The Java API for RESTful Web Services_ �ł��B JAX-RS 2.0 API ��
[JSR 339][5] �ŕW��������AJava EE 7 �Ɋ܂܂�Ă��܂��B ����Aauthlete-java-jaxrs
�́A�F�T�[�o�[�ƃ��\�[�X�T�[�o�[���������邽�߂̃��[�e�B���e�B�[�N���X�Q��񋟂���I�[�v���\�[�X���C�u�����ł��B
authlete-java-jaxrs �� [authlete-java-common][6] ���C�u�������g�p���Ă���A�������
[Authlete Web API][7] �Ƃ��Ƃ肷�邽�߂̃I�[�v���\�[�X���C�u�����ł��B

�N���C�A���g�A�v���P�[�V�������񎦂����A�N�Z�X�g�[�N���̗L�����𒲂ׂ邽�߁A
���̃��\�[�X�T�[�o�[�� Authlete �T�[�o�[�ɖ₢���킹�������Ȃ��܂��B
����͂܂�A���̃��\�[�X�T�[�o�[�́A�A�N�Z�X�g�[�N���𔭍s�����F�T�[�o�[��
Authlete ���o�b�N�G���h�T�[�r�X�Ƃ��Ďg�p���Ă��邱�Ƃ����҂��Ă��邱�Ƃ��Ӗ����܂��B
[java-oauth-server][8] �͂��̂悤�ȔF�T�[�o�[�̎����ł���A[OAuth 2.0][9] ��
[OpenID Connect][10] ���T�|�[�g���Ă��܂��B


���C�Z���X
----------

  Apache License, Version 2.0


�\�[�X�R�[�h
------------

  <code>https://github.com/authlete/java-resource-server</code>


Authlete �ɂ���
-----------------

[Authlete][11] (�I�[�X���[�g) �́AOAuth 2.0 & OpenID Connect
�̎������N���E�h�Œ񋟂���T�[�r�X�ł� ([overview][12])�B Authlete
���񋟂���f�t�H���g�������g�����Ƃɂ��A�������� [java-oauth-server][8]
�ł����Ȃ��Ă���悤�� [Authlete Web API][7]
��p���ĔF�T�[�o�[�������Ŏ������邱�Ƃɂ��AOAuth 2.0 �� OpenID Connect
�̋@�\���ȒP�Ɏ����ł��܂��B

���̔F�T�[�o�[�̎������g���ɂ́AAuthlete ���� API
�N���f���V�����Y���擾���A`authlete.properties` �ɐݒ肷��K�v������܂��B
API �N���f���V�����Y���擾����菇�͂ƂĂ��ȒP�ł��B
�P�ɃA�J�E���g��o�^���邾���ōς݂܂� ([�T�C���A�b�v][13])�B
�ڍׂ� [Getting Started][14] ���Q�Ƃ��Ă��������B


���s���@
--------

1. ���̃��\�[�X�T�[�o�[�̎������_�E�����[�h���܂��B

        $ git clone https://github.com/authlete/java-resource-server.git
        $ cd java-resource-server

2. �ݒ�t�@�C����ҏW���� API �N���f���V�����Y���Z�b�g���܂��B

        $ vi authlete.properties

3. [http://localhost:8081/][15] �Ń��\�[�X�T�[�o�[���N�����܂��B

        $ mvn jetty:run &

`java-resource-server` �� `authlete.properties` ��ݒ�t�@�C���Ƃ��ĎQ�Ƃ��܂��B
���̃t�@�C�����g�p�������ꍇ�́A���̂悤�ɂ��̃t�@�C���̖��O���V�X�e���v���p�e�B�[
`authlete.configuration.file` �Ŏw�肵�Ă��������B

    $ mvn -Dauthlete.configuration.file=local.authlete.properties jetty:run &


�G���h�|�C���g
--------------

���̎����́A���\�Ɏ����G���h�|�C���g�����J���܂��B

| �G���h�|�C���g             | �p�X                      |
|:---------------------------|:--------------------------|
| ���[�U�[���G���h�|�C���g | `/api/userinfo`           |
| �J���g���[�G���h�|�C���g   | `/api/country/{���R�[�h}` |


#### ���[�U�[���G���h�|�C���g

���[�U�[���G���h�|�C���g�́A[OpenID Connect Core 1.0][2] ��
[5.3. UserInfo Endpoint][1] �ɋL�q����Ă���v�������������������̂ł��B

���̃G���h�|�C���g�́A�A�N�Z�X�g�[�N���� Bearer Token �Ƃ��Ď󂯎��܂��B
�܂�A`Authorization: Bearer {�A�N�Z�X�g�[�N��}`
����āA�������̓��N�G�X�g�p�����[�^�[ `access_token={�A�N�Z�X�g�[�N��}`
�ɂ��A�N�Z�X�g�[�N�����󂯎��܂��B �ڍׂ� [RFC 6750][20] ���Q�Ƃ��Ă��������B

���̃G���h�|�C���g�́A�N���C�A���g�A�v���P�[�V�����̐ݒ�ɉ����āA���[�U�[����
JSON �`���������� [JWT][18] �`���ŕԂ��܂��B �N���C�A���g�A�v���P�[�V�����̃��^�f�[�^��
`userinfo_signed_response_alg` �� `userinfo_encrypted_response_alg`
�̗����Ƃ��w�肳��Ă��Ȃ���΁A���[�U�[���͑f�� JSON �ŕԂ���܂��B
�����łȂ��ꍇ�́A�V���A���C�Y���ꂽ JWT �ŕԂ���܂��B Authlete
�̓N���C�A���g�A�v���P�[�V�����̃��^�f�[�^���Ǘ����邽�߂� Web �R���\�[��
([Developer Console][19]) ��񋟂��Ă��܂��B
�N���C�A���g�A�v���P�[�V�����̃��^�f�[�^�ɂ��ẮA
[OpenID Connect Dynamic Client Registration 1.0][22] �� [2. Client Metadata][21]
���Q�Ƃ��Ă��������B

�G���h�|�C���g����Ԃ���郆�[�U�[���ɂ́A���[�U�[��[�N���[��][27] ���܂܂�Ă��܂��B
��Z�Ɍ����ƁA_�N���[��_�Ƃ́A���O�⃁�[���A�h���X�Ȃǂ́A���[�U�[�Ɋւ�����ł��B
Authlete �� (OpenID Connect ���T�|�[�g���Ă���ɂ�������炸)
���[�U�[�f�[�^���Ǘ����Ȃ��̂ŁA���Ȃ����N���[���l��񋟂��Ȃ���΂Ȃ�܂���B
����́A`UserInfoRequestHandlerSpi` �C���^�[�t�F�[�X���������邱�Ƃł����Ȃ��܂��B

���̃��\�[�X�T�[�o�[�̎����ł́A`UserInfoRequestHandlerSpiImpl` �� `UserInfoRequestHandlerSpi`
�C���^�[�t�F�[�X�̎����ŁA�_�~�[�f�[�^�x�[�X����N���[���l�����o���Ă��܂��B
���ۂ̃��[�U�[�f�[�^�x�[�X���Q�Ƃ���悤�A���̎�����ύX����K�v������܂��B


#### �J���g���[�G���h�|�C���g

���̃��\�[�X�T�[�o�[�Ɏ�������Ă���J���g���[�G���h�|�C���g�́A
�ی샊�\�[�X�G���h�|�C���g�̈��ɉ߂��܂���B
��ȖړI�́A�ی샊�\�[�X�G���h�|�C���g�ɂ�����A�N�Z�X�g�[�N���̗L�����̊m�F���@���������Ƃł��B
��̓I�ɂ́A`BaseResourceEndpoint` �N���X�� `extractAccessToken` ���\�b�h��
`validateAccessToken` ���\�b�h�̎g�������������Ƃł��B

�J���g���[�G���h�|�C���g�̃p�X�� `/api/country/{���R�[�h}` �ŁA`{���R�[�h}` �̕�����
[ISO 3166-1 �R�[�h][23]�ł� ([alpha-2][24]�A[alpha-3][25] �܂��� [numeric][26])�B
�Ⴆ�΁A`JP`�A`JPN`�A`392` �͗L���� ISO 3166-1 �R�[�h�ŁA�����͑S�ē��{��\���܂��B
�ł��̂ŁA���� URL �̓J���g���[�G���h�|�C���g�ɑ΂���L���ȃ��N�G�X�g�ł��B

    http://localhost:8081/api/country/JP?access_token={access-token}

�G���h�|�C���g����̉����� JSON �ŁA`{���R�[�h}` �Ŏw�肳��鍑�Ɋւ��鎟�̏����܂�ł��܂��B

  1. ����
  2. ISO 3166-1 alpha-2 �R�[�h
  3. ISO 3166-1 alpha-3 �R�[�h
  4. ISO 3166-1 numeric �R�[�h
  5. Currency

���Ɏ����͉̂�����ł��B

```javascript
{
  "name": "Japan",
  "alpha2": "JP",
  "alpha3": "JPN",
  "numeric": 392,
  "currency": "JPY"
}
```

Web API �� OAuth �̃A�N�Z�X�g�[�N���ŕی삷����@�Ɋւ����ʓI�ȏ�񂨂��
Authlete �ŗL�̏��ɂ��ẮA[Authlete Definitive Guide][17] ��
[Protected Resource][16] ���Q�Ƃ��Ă��������B


�J�X�^�}�C�Y
------------

�V�����ی샊�\�[�X�G���h�|�C���g��ǉ�����ł��ȒP�ȕ��@�́A`CountryEndpoint`
�������Ȃ��Ă���悤�ɁA`BaseResourceEndpoint` �̃T�u�N���X���쐬������@�ł��B
�������A�������A���� `AcessTokenValidator` ([authlete-java-jaxrs][4]) ���g�p������
`AuthleteApi.introspection(IntrospectionRequest)` API ([authlete-java-common][6])
���R�[�����Ă����܂��܂���B

�V�����ی샊�\�[�X�G���h�|�C���g��ǉ�����ɏ]���A�V�����X�R�[�v��ǉ��������Ǝv���ł��傤�B
���Ȃ��� Web API �p�ɐV�����X�R�[�v��ǉ�����ɂ́A[Service Owner Console][28]
���g�p���Ă��������B


���̑��̏��
------------

- [Authlete][11] - Authlete �z�[���y�[�W
- [authlete-java-common][6] - Java �p Authlete ���ʃ��C�u����
- [authlete-java-jaxrs][4] - JAX-RS (Java) �p Authlete ���C�u����
- [java-oauth-server][8] - �F�T�[�o�[�̎���


�T�|�[�g
--------

[Authlete, Inc.][11]<br/>
support@authlete.com


[1]: http://openid.net/specs/openid-connect-core-1_0.html#UserInfo
[2]: http://openid.net/specs/openid-connect-core-1_0.html
[3]: http://tools.ietf.org/html/rfc6750
[4]: https://github.com/authlete/authlete-java-jaxrs
[5]: https://jcp.org/en/jsr/detail?id=339
[6]: https://github.com/authlete/authlete-java-common
[7]: https://www.authlete.com/documents/apis
[8]: https://github.com/authlete/java-oauth-server
[9]: http://tools.ietf.org/html/rfc6749
[10]: http://openid.net/connect/
[11]: https://www.authlete.com/
[12]: https://www.authlete.com/documents/overview
[13]: https://so.authlete.com/accounts/signup
[14]: https://www.authlete.com/documents/getting_started
[15]: http://localhost:8081/
[16]: https://www.authlete.com/documents/definitive_guide/protected_resource
[17]: https://www.authlete.com/documents/definitive_guide
[18]: http://tools.ietf.org/html/rfc7519
[19]: https://www.authlete.com/documents/cd_console
[20]: http://tools.ietf.org/html/rfc6750
[21]: http://openid.net/specs/openid-connect-registration-1_0.html#ClientMetadata
[22]: http://openid.net/specs/openid-connect-registration-1_0.html
[23]: http://en.wikipedia.org/wiki/ISO_3166-1
[24]: http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2
[25]: http://en.wikipedia.org/wiki/ISO_3166-1_alpha-3
[26]: http://en.wikipedia.org/wiki/ISO_3166-1_numeric
[27]: http://openid.net/specs/openid-connect-core-1_0.html#Claims
[28]: https://www.authlete.com/documents/so_console
