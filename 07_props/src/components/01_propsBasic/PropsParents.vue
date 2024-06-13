<template>
    <div :class="{container: true, dark: darkState}">
        props 입력: <input v-model="message"/>
        <PropsChild :message="message"/>
        <DarkMode @toggle="toggleDarkMode"/>
        <ReadProps :readValue="readValue"/>
        부모의 readValue: <input v-model="readValue"/>
    </div>
</template>

<!-- 
    부모에서 자식 컴포넌트로 데이터를 전달하는 경우, 다양한 <slot>을 이용 컨텐츠(또는 구조)를 전달하는 경우에 적합하고 전달받은 데이터 조작도 어려움
    props: 데이터만을 전달하기 위한 용도로 props 사용
    props는 자식에게 물려주면 자식 컴포넌트는 read only(읽기만 가능)로 써야한다. 
    vue는 자식 컴포넌트가 물려받은 값을 수정해도 어차피 부모 컴포넌트에게 영향을 주지 X
 -->
 
<script setup>
    import { ref } from 'vue';
    import PropsChild from './PropsChild.vue';
    import DarkMode from '../DarkMode.vue';
    import ReadProps from './ReadProps.vue';
    
    const message = ref('hello');
    const darkState = ref(false);
    const readValue = ref('vue');

    function toggleDarkMode() {
        darkState.value = !darkState.value;
    }
</script>

<style scoped>
.container {
    border: 1px solid;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.dark {
    background-color: black;
    color: white;
}
</style>