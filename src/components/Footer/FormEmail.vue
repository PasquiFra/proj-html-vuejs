<script>
export default {
    name: 'FormEmail',
    data: () => ({
        email: '',
        registrationMessage: ''
    }),
    methods: {
        registerEmail() {
            this.registrationMessage = 'Your submission was successful.'
            this.email = '';
        }
    }
}
</script>

<template>
    <div class="email-form">
        <h5>subrscibe to newsletter</h5>
        <form>
            <div class="mb-3">
                <input v-model="email" type="email" class="form-control" placeholder="Email">
                <button @click="registerEmail" type="button" class="btn btn-secondary shadow fw-bold">SUBSCRIBE</button>
                <p v-if="registrationMessage">{{ registrationMessage }}</p>
            </div>
        </form>
    </div>
</template>

<style lang="scss"scoped>
h5 {
    text-transform: uppercase;
    margin-bottom: 1rem;
}

input {
    height: 3rem;
    margin-bottom: 1rem;
}

button {
    width: 100%;
    height: 3rem;
    background-color: #545454;
    border: none;

    &:hover {
        color: #bf1d2e;
        background-color: white;
    }
}

p {
    font-size: 1.2rem;
}
</style>