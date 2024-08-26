## FE 프로젝트와 JS
---------------------
아주 간단한 모달 창의 JS 코드는 다음과 같다

```
// 모달 엘리먼트와 버튼을 가져옵니다.
const modal = document.getElementById('myModal');
const openModalBtn = document.getElementById('openModalBtn');
const closeBtn = document.querySelector('.close-btn');

// 버튼 클릭 시 모달을 엽니다.
openModalBtn.onclick = function() {
    modal.style.display = 'block';
}

// 모달의 닫기 버튼 클릭 시 모달을 닫습니다.
closeBtn.onclick = function() {
    modal.style.display = 'none';
}

// 모달 외부 클릭 시 모달을 닫습니다.
window.onclick = function(event) {
    if (event.target === modal) {
        modal.style.display = 'none';
    }
}
```

틀은 대강 알았으니 적용해 봐야지 하고 적용해보는데 안된다

찾아보니까 클래스 선택할때는 `getElementsByClassName`를 사용해야 한다고 하네? 내가 너무 멍청했다

그래도 안된다 아무리 해도 모달이 동작 안해서 GPT한테 물어보기로 했다

```
당신의 코드에서 모달 기능이 잘 작동하지 않는 부분이 있습니다. 

getElementsByClassName은 HTMLCollection을 반환하며, 이 HTMLCollection은 배열이 아니라서 

.onclick 메서드를 직접 사용할 수 없습니다. 이로 인해 모달을 열기 위한 버튼 클릭 시 문제가 발생할 수 있습니다. 

이를 수정하기 위해 getElementsByClassName 대신 querySelectorAll을 사용하여 여러 버튼을 처리할 수 있습니다.

여기서는 querySelectorAll을 사용하여 subsbtn 클래스를 가진 모든 버튼에 대해 모달을 여는 기능을 추가하고, 

getElementById를 사용하여 모달과 닫기 버튼을 조작하는 방법을 보여드리겠습니다.
```

당신의 코드 매우 허접하다며 기계한테 혼났다

요컨데 `.onclick` 메서드는 `getElementById`를 통해 ID를 선택해야 하나보다 

클래스 쓰려면 `querySelectorAll` 써서 여러 버튼을 처리하라는거고 다 용도가 나뉘어져 있었다 정말 하나도 기억 안난다.

그렇게 받은 코드를 보니

```
// 모달 요소
const modal = document.getElementById('subsmodal');

// 모든 'subsbtn' 클래스를 가진 버튼을 가져오기
const openModalBtns = document.querySelectorAll('.subsbtn');

// 모달을 여는 함수
const openModal = () => {
  modal.style.display = 'block';
};

// 모든 버튼에 클릭 이벤트 추가
openModalBtns.forEach(btn => {
  btn.addEventListener('click', (e) => {
    e.preventDefault();
    openModal();
  });
});

// 모달 닫기 버튼
const closeBtn = document.querySelector('.close-btn');

// 모달을 닫는 함수
const closeModal = () => {
  modal.style.display = 'none';
};

// 닫기 버튼 클릭 시 모달을 닫기
closeBtn.addEventListener('click', closeModal);

// 모달 외부 클릭 시 모달을 닫기
window.addEventListener('click', (event) => {
  if (event.target === modal) {
    closeModal();
  }
});
```

내가 적용한 간단한 예시보다 조금 달라져 버렸고 왜 이렇게나 차이가 나게 만들어줬는지 궁금했다

###1. `window.onclick` 와 `window.addEventListener`의 차이
    * `window.onclick`는 단일 이벤트 핸들러만 설정 가능하고, 이미 설정된 핸들러가 있으면 덮어쓰게 된다
    * `window.addEventListener` 는 이벤트 리스너를 추가하는 메서드라 여러개의 이벤트 핸들러를 동일한 이벤트에 등록 가능하고, 각각의 핸들러가 독립적으로 동작한다
    * 정리하면 `window.addEventListener` 가 여러 상황에서 더 유연하니 이걸 쓰는게 좋다는 것
###2. forEach를 통해 여러 버튼에 이벤트 부여
    * 모달 열기 이벤트는 여러 상황에서 추가적으로 쓰일 수 있으니 사이트 유지보수를 생각한다면 확실히 이게 좋은 듯 하다

