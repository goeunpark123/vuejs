<script setup>
    import {RouterLink, RouterView} from 'vue-router';

</script>
<!-- 
  RouterLink: 사용자가 다른 라우트로 이동할 수 있도록 하는 링크 생성에 사용
  RouterLink의 속성
  to: 이동할 라우트 경로(uri)
  active-class: 현재 라우트와 일치할 때 적용할 css 클래스 지정(활성화 되었던 RouterLink에 css 적용 시 사용)

  RouterView: 현재 라우트에 해당하는 컴포넌트를 렌더링하는 지점을 정하기 위해 사용
  vue-router가 현재 uri에 따라 매칭되는 컴포넌트를 찾으면, 해당 컴포넌트를 RouterView 내부에 렌더링하여 페이지 간의 전환 구현 가능
  
  RouterView는 RouterLink와 함께 사용되어 라우팅 기능 완성
 -->
<template>
  <header>
    <h1>Router 사용</h1>
    <hr>
    <div class="wrapper">
      <!-- <nav>
        <h2>basic router</h2>
            <RouterLink to="/" active-class="active" replace>Home</RouterLink>
            <RouterLink to="/pathvariable/1" active-class="active">PathVariable</RouterLink>
            <RouterLink to="/querystring??name=홍길동&age=20" active-class="active">QueryString</RouterLink>
        </nav> -->

      <nav>
        <RouterLink to="/" active-class="active">Home</RouterLink>
        <RouterLink to="/nested/home" active-class="active">중첩 인덱스</RouterLink>
        <RouterLink to="/nested/view" active-class="active">중첩 라우터</RouterLink>
      </nav>

    </div>
  </header>
  <main>
    <!-- <RouterView/> -->
  </main>
</template>

<style scoped>
nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
  font-size: 30px;
}

a {
  margin-left: 10px;
}

.active {
  color: red;
}

main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

header {
  text-align: center;
}
</style>
