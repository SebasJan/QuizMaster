<script setup lang="ts">
import Navbar from "../components/Navbar.vue";
import { ref } from "vue";
import axios from "axios";

const email = ref("");
const userName = ref("");
const password = ref("");
const errorMessage = ref();

async function register() {
    // check if all fields are filled in
    if (email.value === "" || userName.value === "" || password.value === "") {
        errorMessage.value = "Vul alle velden in";
        return;
    }

    try {
        const response = await axios.post("/api/users/register", {
            email: email.value,
            username: userName.value,
            password: password.value,
        });
        errorMessage.value = "Registratie gelukt, u kunt nu inloggen";
    } catch (error: any) {
        if (error.response.status === 409) {
            errorMessage.value = "Gebruikersnaam of email bestaat al";
        } else {
            errorMessage.value = "Er is iets misgegaan, probeer het later opnieuw";
        }
    }

}
</script>

<template>
    <div class="container">
        <Navbar />
        <div class="row justify-content-center">
            <div class="col-md-8 col-lg-4">
                <div class="wrap">
                    <div class="login-wrap p-4 p-md-5">
                        <div class="d-flex">
                            <div class="w-200">
                                <h3 class="mb-4">Registreer je hier</h3>
                            </div>
                        </div>
                        <form action="#" class="signin-form">
                            <div class="form-group mt-3">
                                <label class="form-control-placeholder" for="username">Email address*</label>
                                <input type="email" class="form-control" v-model="email" required />
                            </div>
                            <div class="form-group mt-3">
                                <label class="form-control-placeholder" for="username">Gebruikersnaam*</label>
                                <input type="text" class="form-control" v-model="userName" required />
                            </div>
                            <div class="form-group">
                                <label class="form-control-placeholder" for="password">Wachtwoord*</label>
                                <input id="password-field" type="password" class="form-control" v-model="password"
                                    required />
                            </div>
                            <div class="form-group">
                                <button @click="register" type="button"
                                    class="form-control btn btn-primary rounded submit px-3">
                                    Registreer
                                </button>
                            </div>
                        </form>
                        <p>{{ errorMessage }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped></style>