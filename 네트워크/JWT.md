# JWT(Json Web Tocken)
Json Web Tocken은 Json 형식의 토큰이다.

서버에서 따로 저장하지 않는다. 

시간에 따라 변경되지 않는 Stateless이다.

Signature를 해독해서 변형된 Payload가 없는지 확인한다.

``` text
Header.Payload.Signature
```

- Header: 해시 알고리즘, 토큰 타입에 대한 정보

- Payload: 전달하는 데이터 포함, key를 모두 claim이라고 함. registered, public, private

- Signature: `Hash(encode(header)+”.”+encode(payload)+secret)`

인증과 정보 교환을 위해 사용한다.

서명 또는 암호화되어있어 변조되지 않도록 보호한다.

클레임은 토큰에 포함된 정보를 나타내며, 클레임 종류로는 등록된(registered) 클레임, 공개(public) 클레임, 비공개(private) 클레임이 있다.

주로 웹 애플리케이션에서 사용자 인증, 권한 부여 등에 활용한다.

세션을 관리하지 않고도 상태를 유지할 수 있는 이점

단점: 세션 관리는 힘듦. 로그아웃 시키고자 하거나 할 때, 탈취당했을 때 방어가 어려움 → 만료시간. 

따라서 토큰 2개를 활용하는 방식이 나왔다. Refresh Token, Access Token
Access Token의 만료 기간을 짧게 두고 만료되면 Refresh Token으로 재발급 받도록 한다.
