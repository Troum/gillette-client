<template>
  <v-container class=" ma-0 pa-0 fill-height bodyb desctop-class" fluid> 

          
      <v-row class="justify-space-around">
            <v-col cols="11" class="d-flex d-sm-none">
              <v-img
              contain=""
              aspect-ratio="1.5"
              height="55vw"
              src="../assets/m-1.svg"
              >
        
              </v-img>
              <v-btn
              text
              color="white"
              dark=""
              @click="mobMenuToogle"
              >
                <v-icon>mdi-menu</v-icon>
              </v-btn>
              
            
            </v-col>

            
            
          </v-row>

      <v-row class="justify-space-around">
            <v-col cols="12" class="d-flex d-sm-none">
              <v-img
              contain=""
              aspect-ratio="1"
              height="75vw"
              src="../assets/m-1-1.png"
              >
        
              </v-img>
            
            </v-col>
            
          </v-row>
      <v-row class="justify-space-around">
            <v-col cols="12" class="d-flex d-sm-none">
              <v-img
              contain=""
              aspect-ratio="1"
              height="55vw"
              style="margin-top:-20vw;"
              src="../assets/m-1-2.svg"
              >
        
              </v-img>
            
            </v-col>
            
          </v-row>

      <v-row class="justify-space-around">
            <v-col cols="12" class="d-flex d-sm-none">
              <v-img
              contain=""
              aspect-ratio="1"
              height="280vw"
              style="margin-top:-20vw;"
              src="../assets/m-mech.png"
              >
        
              </v-img>
            
            </v-col>
            
          </v-row>
    
      <v-row class="d-none d-md-flex  pa-0 ma-0 d-flex justify-center align-center menu-d">
        <v-col cols="8" class="d-none d-md-flex">
          <v-row class="justify-space-around">
            <v-col cols="2" class="f-sdcreen">
              <v-img
              contain=""
              height="3rem"
              src="../assets/logo.svg"
              >
        
              </v-img>
              <!-- <div class="first-screen1"></div> -->
            </v-col>
            <v-col cols="6"></v-col>
            <v-col cols="2"  class="f-sdcreen pa-0 ma-0 d-flex justify-center align-center">
                <v-btn dark="" text href="rules.dpf" target="_blank">Правила</v-btn>
            </v-col>
            <v-col cols="2" class="f-sdcreen pa-0 ma-0 d-flex justify-center align-center">
                <v-btn dark="" text href="#regform" >Регистрация</v-btn>
            </v-col>
            
          </v-row>
        </v-col>
      </v-row>
    




      <v-row class=" pa-0 ma-0 d-flex justify-center align-center">
        <v-col cols="12" lg="12" xl="9" class="d-none d-md-flex f-screen">
          <v-img
          contain=""
          aspect-ratio="1.5"
          src="../assets/first-screen.svg"
          >
    
          </v-img>
          <!-- <div class="first-screen1"></div> -->
        </v-col>
      </v-row>
  

      <v-row class=" pa-0 ma-0 d-flex justify-center align-center">
        <v-col cols="12" sm="8" class="d-none d-md-flex ">
          
          <v-img
            contain=""
            src="../assets/mech-title.svg"
            class="reg-title"
          ></v-img>
        </v-col>
        <v-col cols="12" lg="11" xl="9" class="d-none d-md-flex s-screen">
          <v-img
          contain=""
          aspect-ratio="1.5"
          src="../assets/meh-v.svg"
          >
    
          </v-img>
          <!-- <div class="first-screen1"></div> -->
        </v-col>
      </v-row>
    



    <!-- ///// REGFORM////// -->
    <a name="regform-mob"></a>
    <v-row class="pa-0 ma-0 d-flex justify-center">
      <v-col cols="12" sm="8" class="d-none d-md-flex "><a name="regform"></a>
        
        <v-img
          contain=""
          src="../assets/reg-title.svg"
          class="reg-title"
        ></v-img>
      </v-col>
      <v-col cols="10" sm="10" md="10" lg="11" xl="8" class="reg-form">
        <v-card flat dark="" color="transparent">
          <validation-observer ref="observer" v-slot="{ passes }">
            <v-form @submit.prevent="passes( submit )" >
              <v-row>
                <v-col cols="12" lg="4">
                  <validation-provider name="Фамилия" rules="required" v-slot="{ errors }">
                    <v-text-field   autocomplete="off" :error-messages="errors"
                                  v-model="form.name"
                                  label="Фамилия*" dense outlined type="text"></v-text-field>
                  </validation-provider>
                  <validation-provider name="Имя" rules="required" v-slot="{ errors }">
                    <v-text-field autocomplete="off" :error-messages="errors"
                                  v-model="form.surname"
                                  label="Имя*" dense outlined type="text"></v-text-field>
                  </validation-provider>
                  <v-text-field autocomplete="off"
                                v-model="form.secondName"
                                label="Отчество" dense outlined type="text"></v-text-field>
                  <validation-provider name="Почтовый адрес" rules="required" v-slot="{ errors }">
                    <v-text-field autocomplete="off" :error-messages="errors"
                                  v-model="form.address"
                                  label="Почтовый адрес*" dense outlined type="text"></v-text-field>
                  </validation-provider>
                </v-col>
                <v-col cols="12" lg="4">
                  <v-row class="ma-0 pa-0">
                    <v-col class="pa-0" cols="2">
                      <validation-provider rules="required" v-slot="{ errors }">
                        <v-text-field autocomplete="off" :error-messages="errors"  v-model="form.phoneCode"
                                      readonly outlined dense type="text"></v-text-field>
                      </validation-provider>
                    </v-col>
                    <v-col class="pa-0" cols="3">
                      <validation-provider name="Код оператора" rules="required" v-slot="{ errors }">
                        <v-select v-model="form.phonePrefix"
                                  :error-messages="errors"
                                  outlined dense :items="$store.getters.mobile.prefixes"></v-select>
                      </validation-provider>
                    </v-col>
                    <v-col class="pa-0" cols="4">
                      <validation-provider name="Номер телефона" rules="required" v-slot="{ errors }">
                        <v-text-field autocomplete="off" :error-messages="errors"  v-model="form.phoneNumber"
                                      data-phone
                                      @keypress="integer"
                                      @input="formatPhone"
                                      placeholder="XXX-XX-XX*"
                                      outlined dense type="text"></v-text-field>
                      </validation-provider>
                    </v-col>
                    <v-col class="pa-0" cols="3">
                      <validation-provider name="Наименование оператора" rules="required" v-slot="{ errors }">
                        <v-select v-model="form.phoneOperator"
                                  :error-messages="errors"
                                  outlined dense :items="$store.getters.mobile.operators"></v-select>
                      </validation-provider>
                    </v-col>
                  </v-row>
                  <validation-provider name="Адрес E-mail" rules="required|email" v-slot="{ errors }">
                    <v-text-field autocomplete="off" :error-messages="errors"
                                  v-model="form.email"
                                  label="E-mail*" dense outlined type="email"></v-text-field>
                  </validation-provider>
                  <validation-provider name="Торговый объект" rules="required" v-slot="{ errors }">
                    <v-select outlined dense :error-messages="errors"
                              label="Торговый объект*"
                              v-model="form.shop" :items="$store.getters.shops"></v-select></validation-provider>
                  <validation-provider name="Фото чека" rules="required" v-slot="{ errors }">
                    <v-file-input
                            :error-messages="errors"
                            dense outlined
                            v-model="form.file"
                            chips
                            show-size
                            accept="image/png, image/jpeg, image/bmp"
                            prepend-icon=""
                            append-icon="mdi-plus"
                    >
                      <template v-slot:label>
                        <span>Загрузить фото чека
                          <v-icon small>mdi-help-circle-outline</v-icon>
                        </span>
                      </template>
                    </v-file-input>
                  </validation-provider>
                </v-col>
                <v-col class="mb-0 pb-0" cols="12" lg="4">
                  <validation-provider name="Стоимость акционного товара" rules="required" v-slot="{ errors }">
                    <v-text-field autocomplete="off" :error-messages="errors"
                                  label="Стоимость акционного товара*"
                                  @keypress="integer"
                                  v-model="form.price"
                                  dense outlined type="text"></v-text-field>
                  </validation-provider>
                  <validation-provider name="Номер чека" rules="required" v-slot="{ errors }">
                    <v-text-field autocomplete="off" :error-messages="errors"
                                  label="Номер чека*"
                                  v-model="form.checkNumber"
                                  dense outlined type="text"></v-text-field>
                  </validation-provider>
                  <v-row class="ma-0 pa-0">
                    <v-col class="ma-0 pa-0 mt-n6" cols="12">
                      <small>Дата совершения покупки*</small>
                    </v-col>
                    <v-col class="ma-0 pa-0" cols="12">
                      <v-row class="ma-0 pa-0">
                        <v-col class="pa-0" cols="3">
                          <validation-provider name="День покупки" rules="required" v-slot="{ errors }">
                            <v-select outlined dense :error-messages="errors"
                                      v-model="form.dayBuy"
                                      :items="$store.getters.days"></v-select></validation-provider>
                        </v-col>
                        <v-col class="pa-0" cols="7">
                          <validation-provider name="Месяц покупки" rules="required" v-slot="{ errors }">
                            <v-select outlined dense :error-messages="errors"
                                      v-model="form.monthBuy"
                                      :items="$store.getters.months"></v-select></validation-provider>
                        </v-col>
                        <v-col class="pa-0" cols="2">
                          <validation-provider name="Год покупки" rules="required" v-slot="{ errors }">
                            <v-text-field autocomplete="off" :error-messages="errors"  v-model="form.year"
                                          readonly outlined dense type="text"></v-text-field>
                          </validation-provider>
                        </v-col>
                      </v-row>
                    </v-col>
                  </v-row>
                  <v-row class="ma-0 pa-0">
                    <v-col class="ma-0 pa-0 mt-n6" cols="12">
                      <small>Дата регистрации заявки на участие в Акции*</small>
                    </v-col>
                    <v-col class="ma-0 pa-0" cols="12">
                      <v-row class="ma-0 pa-0">
                        <v-col class="pa-0" cols="3">
                          <validation-provider name="День регистрации" rules="required" v-slot="{ errors }">
                            <v-select outlined dense :error-messages="errors"
                                      v-model="form.dayRegister"
                                      :items="$store.getters.days"></v-select>
                          </validation-provider>
                        </v-col>
                        <v-col class="pa-0" cols="7">
                          <validation-provider name="Месяц регистрации" rules="required" v-slot="{ errors }">
                            <v-select outlined dense :error-messages="errors"
                                      v-model="form.monthRegister"
                                      :items="$store.getters.months"></v-select>
                          </validation-provider>
                        </v-col>
                        <v-col class="pa-0" cols="2">
                          <validation-provider name="Год регистрации" rules="required" v-slot="{ errors }">
                            <v-text-field autocomplete="off" :error-messages="errors"  v-model="form.year"
                                          readonly outlined dense type="text"></v-text-field>
                          </validation-provider>
                        </v-col>
                      </v-row>
                    </v-col>
                  </v-row>
                </v-col>
                <v-col class="pt-0 mt-n3" cols="12" lg="12">
                  <v-row class="ma-0 pa-0">
                    <v-col cols="12" class="ma-0 pa-0 mt-n6">
                      <small>Акционный товар: наименование продукции*</small>
                    </v-col>
                  </v-row>
                  <v-row class="ma-0 pa-0">
                    <v-col class="pa-0" cols="12" sm="10">
                      <validation-provider name="Наименование акционного товара" rules="required" v-slot="{ errors }">
                        <v-select outlined dense :error-messages="errors"
                                  v-model="form.good"
                                  :items="$store.getters.goods"></v-select>
                      </validation-provider>
                    </v-col>
                    <v-col class="pa-0" cols="3" sm="2">
                      <validation-provider name="Количество акционного товара" rules="required" v-slot="{ errors }">
                        <v-select outlined dense :error-messages="errors"
                                  v-model="form.count" :items="$store.getters.counts"></v-select>
                      </validation-provider>
                    </v-col>
                  </v-row>
                </v-col>
              </v-row>
              <v-row>
                <v-col cols="8" class="mx-auto d-flex justify-center flex-column">
                  <v-checkbox v-model="form.agreementOne" class="mx-auto">
                    <template v-slot:label>
                      <span class="d-block mx-auto">*Регистрируясь, Вы подтверждаете свое согласия на участие в акции.</span>
                    </template>
                  </v-checkbox>
                  <v-checkbox v-model="form.agreementTwo" class="mx-auto">
                    <template v-slot:label>
                      <span class="d-block mx-auto">
                        *Регистрируясь, Вы подтверждаете, что изучили и согласны с <span style="z-index:9;"><a href="rules.pdf" target="_blank">правилами</a></span>  акции.
                      </span>
                    </template>
                  </v-checkbox>
                </v-col>
                <v-col cols="8" class="mx-auto text-center">
                  <v-btn :disabled="!form.agreementOne || !form.agreementTwo"
                         :loading="loading"
                         color="#EC6720" type="submit">
                    <span class="white--text">Зарегистрироваться</span>
                  </v-btn>
                </v-col>
              </v-row>
            </v-form>
          </validation-observer>
        </v-card>
      </v-col>
    </v-row>
    <!-- ///// END  REGFORM////// -->
    <!-- <v-row class=" pa-0 ma-0 d-flex justify-center align-center">
      <v-col cols="12" lg="11" xl="9" class="foo-screen">
        <v-img
        contain=""
        aspect-ratio="1.87"
        src="../assets/footer-d.svg"
        >
  
        </v-img>
      </v-col>
    </v-row> -->
    <v-footer
      absolute
      class="d-none d-md-flex font-weight-medium"
      
      color="transparent"
      padless
    >
      <v-col
        class="text-center"
        cols="12"
        
      >
        <v-img
        src="../assets/footer-d.svg"
        min-height="15rem"
        contain=""
        aspect-ratio="2.5"
        >

        </v-img>
      </v-col>
    </v-footer>

    <v-row class="justify-space-around">
            <v-col cols="12" class="d-flex d-sm-none">
              <v-img
              contain=""
              aspect-ratio="1.5"
              height="105vw"
              style="margin-top:-60vw"
              src="../assets/m-footer.png"
              >
        
              </v-img>
            
            </v-col>
            
          </v-row>

          <v-card
            v-if="mMenu"
            class="mx-auto menu-mob"
            max-width="400"
            tile
          >
              <v-list-item>
                <v-list-item-content>
                  <v-btn text href="rules.dpf" target="_blank" @click="mobMenuToogle">Правила</v-btn>
                </v-list-item-content>
              </v-list-item>

              <v-list-item two-line>
                <v-list-item-content>
                  <v-btn text href="#regform-mob" @click="mobMenuToogle">Регистрация</v-btn>
                </v-list-item-content>
              </v-list-item>
          </v-card>


    
  </v-container>
</template>

<script>
  import Cleave from 'cleave.js';
  export default {
    name: 'Home',
    data() {
      return {
        mMenu: false,
        loading: false,
        form: {
          name: null,
          surname: null,
          secondName: null,
          address: null,
          email: null,
          shop: null,
          phoneCode: '+375',
          phonePrefix: this.$store.getters.mobile.prefixes[1].value,
          phoneNumber: null,
          phoneOperator: this.$store.getters.mobile.operators[0].value,
          year: 2020,
          monthRegister: Number(new Date().toLocaleDateString('ru', {month: 'numeric'})),
          dayRegister: Number(new Date().toLocaleString('ru', { day: 'numeric' })),
          monthBuy: Number(new Date().toLocaleDateString('ru', {month: 'numeric'})),
          dayBuy: Number(new Date().toLocaleString('ru', { day: 'numeric' })),
          file: null,
          price: null,
          checkNumber: null,
          good: this.$store.getters.goods[0].value,
          goodText: this.$store.getters.goods[0].text,
          count: this.$store.getters.counts[0].value,
          agreementOne: false,
          agreementTwo: false,
        }
      }
    },
    methods: {
      mobMenuToogle(){
        this.mMenu = !this.mMenu;
        console.log (!this.mMenu)
      },
      submit(){
        this.loading = true;
        this.$httpService.post('api/participate', this.$fdService.fill(this.form))
            .then(response => {
              this.$refs.observer.reset();
              this.$store.commit('alert', {message: response.data.success, });
              this.$fdService.reset(this.form);
            })
            .finally(() => {
              this.loading = false
            })
      },
      integer(event) {
        event = (event) ? event : window.event;
        let charCode = (event.which) ? event.which : event.keyCode;
        if ((charCode > 31 && (charCode < 48 || charCode > 57)) && charCode !== 46) {
          event.preventDefault();
        } else {
          return true;
        }
      },
      formatPhone() {
        new Cleave('[data-phone]', {
          delimiter: '-',
          blocks: [3, 2, 2]
        })
      }
    }
  }
</script>

<style>
.menu-mob {
  position: absolute;
  top: 3rem;
  right: 2rem;
}
.menu-d {
  z-index: 9;
}
  .first-screen {
    background-image: url(../assets/first-screen.svg);
    max-height: 70rem;
    position: relative;
    margin-top: -26rem;
    width: 50rem;
  }
  .f-screen {
    margin-top: -2.5rem;
  }
  .s-screen {
    margin-top: -6rem;
  }
  .reg-title {
    margin-top: 7rem;
    margin-bottom: 4rem;
    z-index: 999;
  }
  .reg-title .v-responsive__sizer{
    margin-bottom: 3rem;
  }
  .foo-screen v-image v-responsive__sizer {
    padding: 0;
  }
  .foo-screen {
    margin-bottom: -40rem!important;
    max-height: 10rem;
  }
  .v-responsive__sizer {
    /* padding-bottom: 10px!important; */
    margin-bottom: -22rem;
  }
  .reg-form {
    margin-bottom: 17rem;
    z-index: 9;
    font-size: 1rem;
  }
  .v-input__slot fieldset {
    border: solid 1px #EC6720;
  }
  .v-input__append-inner .v-input__icon--append {
    background-color: #EC6720;
  }
  .v-select__selections {
    font-size: .85rem;
  }
  @media screen and (max-width: 901px) {
    .desctop-class {
      display: none;
    }
  }
</style>
