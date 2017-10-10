---
layout: post
title: UserDefaults
---

#UserDefaults

```swift

//데이터 불러오기
open func object(forKey defaultName: String) -> Any?
open func string(forKey defaultName: String) -> String?
open func array(forKey defaultName: String) -> [Any]?

//데이터 저장하기
open func set(_ value: Any?, forKey defaultName: String)

//데이터 지우기
open func removeObject(forKey defaultName: String)
```

plist 에 저장됨

주로 앱에서 설정하는 환경설정, 옵션 같은 걸 저장하는 용도로 많이 씀


```swift
var list:[[String: String]] = []
      if let tempList = UserDefaults.standard.array(forKey: "UserList") as? [[String: String]] {
        list = tempList
      } else {
        list = []
      }
      let userData:[String: String] = ["ID": accoutname, "PW": accounpassword]
      list.append(userData)
      UserDefaults.standard.set(list, forKey: "UserList")
```

사용하는 예제를 보자면 딕셔너리로 많이 넘기고 특히나 type 처리를 잘해줘야 한다. (type 명시 명확히~!!!)