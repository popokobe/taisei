<template>
    <form @submit.prevent>
        <div class="form-item">
            <label for="">氏名</label>
            <div class="control">
                <input v-model="form.name" type="text">
            </div>
        </div>
        <div class="form-item">
            <label for="">メールアドレス</label>
            <div class="control">
                <input v-model="form.email" type="email">
            </div>
        </div>
        <div class="form-item">
            <label for="">お問い合わせ内容</label>
            <div class="control">
                <textarea name="" rows="8"></textarea>
            </div>
        </div>
        <div class="submit">
            <button type="submit" @click="$emit('confirm')">入力内容を確認</button>
        </div>
    </form>
</template>

<script>
export default {
    data() {
        return {
            form: {
                name: "",
                email: "",
                content: ""
            }
        }
    }
}
</script>

<style lang="scss" scoped>
form {
    .form-item {
        margin-bottom: 30px;

        label {
            font-size: 1.3rem;
            font-weight: 500;
            display: inline-block;
            margin-bottom: 7px;
        }

        input,
        textarea {
            background-color: $bg-clr-sub;
            border: 1px solid $border-clr-main;
            border-radius: 5px;
            font-size: 1.6rem;
            line-height: 2;
            padding: .5rem 1.5rem;
        }
        
        input {
            width: 100%;
            max-width: 200px;

            &[type*="email"] {
                max-width: 325px;
            }
        }

        textarea {
            width: 100%;
        }
    }

    .submit {
        display: flex;
        justify-content: center;

        button {
            font-weight: 500;
            font-size: 1.4rem;
            padding: 0 2rem;
            display: inline-block;
            min-width: 120px;
            color: $bg-clr-sub;
            background-color: $clr-main;
            height: 45px;
            text-align: center;
            border-radius: 40px;
        }
    }
}
</style>