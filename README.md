# FlippingLabel
UILabel acting like a "flipping clock"  tile


![alt tag](https://github.com/Melomat/FlippingLabel/blob/master/FlippingLabel.gif)

Requirements

FlippingLabel requires Xcode 8, targeting iOS 9.0



***



기존 FlippingLabel을 fork하여 수정하였습니다.



**수정사항**

- FlippingLabel을 코드로 생성시 크기를 가지고 있어야함. --> 없어도 생성 가능하게 수정 
- 코너에 라운드 효과를 주면, 애니메이션 시작시 생성했을 때의 각진 형태에서 시작해서 애니메이션이 끝나면서 라운드 효과가 입혀짐 --> 애니메이션때도 둥근 형태 유지하게 수정
- 애니메이션을 빠르게 넘길 시 애니메이션이 겹치면서 오류 & 하단 뷰가 남음 --> 기존 애니메이션을 중지시키고 다시 새롭게 시작하게 수정



> 최대한 기존 코드를 유지하는 형태에서 수정할 수 있도록 노력함



Usage
------

To use this Label, just import FlippingLabel.swift to your project.
Once imported, add a UILabel into your storyboard/xib file, and change it's class to FlippingLabel.

To change the label text using a fliping animation, just call the updateWithText() method on your FlippingLabel like so :
```Swift
myLabel.updateWithText("My awesome text")
```
It will automatically animate your label text with a nice flipping animation



***



**코드로 작성시**



```swift
// 생성
let flipLabel = FlippingLabel()
flipLabel.translatesAutoresizingMaskIntoConstraints = false

// 화면에 추가
self.view.addSubview(self.flipLabel)

// 크기 설정
NSLayoutConstraint.activate([
    self.flipLabel.widthAnchor.constraint(equalToConstant: 200),
    self.flipLabel.heightAnchor.constraint(equalToConstant: 200),
    self.flipLabel.centerYAnchor.constraint(equalTo: self.view.centerYAnchor),
    self.flipLabel.centerXAnchor.constraint(equalTo: self.view.centerXAnchor)
])

// 숫자 변화
self.flipLabel.updateWithText("\(10)")
```



Feedback
------

  * If you found a **bug**, open an **issue**
  * If you have a **feature request**, open an **issue**
  * If you want to **contribute**, submit a **pull request**

Contact
------

* [@melomat](https://github.com/melomat/) on github

License
------

FlippingLabel is under the MIT license. See the LICENSE file for more information.
