//6769203898:AAHPB1t9F1e_sEN_91anJZjPbBEAOqdcpjQ
//793884500


<script setup>
import { ref } from 'vue';
const name = ref('');
const question = ref(''); 
const phone = ref(''); 
const email = ref('');
const succsess=ref(false);

async function onSubmit(){
    console.log(name.value, question.value, phone.value, email.value);
    const BotToken="6769203898:AAHPB1t9F1e_sEN_91anJZjPbBEAOqdcpjQ";
    const ChatId="793884500";
    const text="Новое сообщение:%0A%0A" + `Вопрос: ${question.value}%0A` +`Имя: ${name.value}%0A` +`Телефон: ${phone.value}%0A` +`Почта: ${email.value}`;
    //https://api.telegram.org/bot<Bot_token>/sendMessage?chat_id=<chat_id>&text=Привет%20мир
    await fetch(`https://api.telegram.org/bot${BotToken}/sendMessage?chat_id=${ChatId}&text=${text}`)
    .then ((responce)=>{
        if (responce.status===200){
            succsess.value=true;
        }
    })
    .catch((error)=>{
        succsess.value=false;
        console.log(error);
    });
    const message = succsess.value ? "Отправлено": "Ошибка!";
    alert(message);
    name.value ='';
    question.value='';
    phone.value='';
    email.value='';
}   
</script>

<template>
    <section class="feedback">
        <div class="container">
            <div class="row">
                <div class="col-xl-6">
                    <div class="feedback__text">
                        <h2>Остались вопросы?</h2>
                        <p>Свяжитесь с нами!</p>
                    </div>
                </div>

                <div class="col-xl-6">
                    <form action="#" class="feetback__form" method="post" @submit.prevent="onSubmit">
                        <textarea placeholder="Введите ваш запрос" required v-model="question"></textarea>
                        <div class="feetback__form-group">
                            <input type="text" placeholder="Ваше имя" required title="Введите ваше имя" v-model="name">
                            <input type="tel" placeholder="+7(___)___-____" required pattern="[0-9]{11}"
                                title="Введите ваш номер телефона" v-model="phone">
                            <input type="email" placeholder="Электронная почта" required
                                title="Введите вашу электронную почту" v-model="email">
                        </div>

                        <button class="button-prime" type="submit">Отправить</button>
                    </form>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped></style>