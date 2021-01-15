<template>
  <div class="home">
    <!-- Mapa  -->
    <section id="map-container-demo-section" class="z-depth-1-half map-container-section mb-4" style="height: 500px">
      <iframe
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3657.027661773113!2d-46.6867650495951!3d-23.567449984604618!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x94ce57767baaad8f%3A0x75e6fbbf92938efd!2sR.%20Cap.%20Ant%C3%B4nio%20Rosa%2C%20376%20-%20Cj.%20101%20-%20Pinheiros%2C%20S%C3%A3o%20Paulo%20-%20SP%2C%2001443-900!5e0!3m2!1spt-PT!2sbr!4v1610230983876!5m2!1spt-PT!2sbr"
          frameborder="0" style="border:0"></iframe>
    </section>
    <!--  conteúdo pagina  -->
    <main>
      <div class="container-fluid mb-5">
        <div class="row" style="margin-top: -100px;">
          <div class="col-md-12">
            <div class="card pb-5">
              <div class="card-body">
                <div class="container">
                  <!--Section: Contact-->
                  <section class="section">
                    <!--Section heading-->
                    <h2 class="font-weight-bold text-center h1 my-5">
                      fale com um especialista Netshow.me
                    </h2>
                    <!--Section description-->
                    <p class="text-center grey-text mb-5 mx-auto w-responsive">
                      Agora o seu conhecimento pode
                      virar conteúdo, engajar o seu público de maneira
                      inovadora e ainda ser uma fonte de
                      receita escalável. Fale com um dos nossos especialistas
                      para conhecer cases de
                      sucesso e entender como impusionar seu negócio.</p>
                    <div class="row pt-5">
                      <div class="col-md-8 col-xl-9">
                        <div class="container">
                          <div class="row">
                            <div class="col-10">
                              <message-box color="pink">
                                Como podemos te ajudar?
                              </message-box>
                            </div>
                            <div class="col-2">
                              <img width="46" src="@/assets/images/logo-small.png" alt="">
                            </div>
                          </div>
                        </div>
                        <!--formulario-->
                        <form @submit.prevent="checkForm"
                              v-if="showForm"
                              enctype="multipart/form-data">
                          <div class="row">
                            <div class="col-md-10">
                              <!--container formato mensagem azul-->
                              <message-box color="form-blue">
                                <div class="row">
                                  <div class="col-md-6">
                                    <div class="md-form">
                                      <input type="text"
                                             v-model="contact_name"
                                             name="contact_name"
                                             id="contact_name"
                                             maxlength="100"
                                             class="form-control"
                                             placeholder="seu nome aqui"
                                      >
                                    </div>
                                  </div>
                                  <div class="col-md-6">
                                    <div class="md-form">
                                      <input type="email"
                                             maxlength="100"
                                             v-model="contact_email"
                                             name="contact_email"
                                             id="contact_email"
                                             class="form-control"
                                             placeholder="seu email aqui"
                                      >
                                    </div>
                                  </div>
                                </div>
                                <div class="row">
                                  <div class="col-md-8">
                                    <div class="md-form">
                                      <input type="text"
                                             maxlength="100"
                                             v-model="contact_subject"
                                             name="contact_subject"
                                             id="contact_subject"
                                             class="form-control"
                                             placeholder="Assunto"
                                      >
                                    </div>
                                  </div>
                                  <div class="col-md-4">
                                    <div class="md-form">
                                      <input type="tel"
                                             maxlength="20"
                                             v-model="contact_telephone"
                                             name="contact_telephone"
                                             id="contact_telephone"
                                             class="form-control"
                                             placeholder="Telefone"
                                      >
                                    </div>
                                  </div>
                                </div>
                                <div class="row">
                                  <div class="col-md-12">
                                    <div class="md-form">
                                      <textarea type="text"
                                                maxlength="800"
                                                id="contact_message"
                                                v-model="contact_message"
                                                name="contact_message"
                                                class="md-textarea form-control"
                                                rows="3"
                                                placeholder="Escreva sua mensagem aqui"

                                      ></textarea>
                                    </div>
                                  </div>
                                </div>
                                <div class="row">
                                  <div class="col-md-12">
                                    <div class="md-form text-center">
                                      <input type="file"
                                             v-on:change="handleFileUpload()"
                                             ref="file"
                                             name="contact_attachment" id="contact_attachment"
                                             class="form-control-file"
                                             accept=".pdf,.doc,.docx,.odt, .txt"
                                             required></div>
                                  </div>
                                </div>
                              </message-box>
                              <br>
                              <!--botão enviar-->
                              <div class="row">
                                <div class="col-md-12">
                                  <div class="text-center text-md-left">
                                    <button
                                        class="pink-gradient btn"
                                    >
                                      Enviar <i class="far fa-paper-plane fa-2x"></i>
                                    </button>
                                  </div>
                                </div>
                              </div>
                            </div>
                          </div>
                          <!--container formato mensagem que recebe os erros do formulario-->
                          <div v-if="errors.length" class="container">
                            <div class="row">
                              <div class="col-10">
                                <message-box color="pink">
                                  <div class="message-content">
                                    <p>
                                      <b>Por favor, corrija o(s) seguinte(s) erro(s):</b>
                                    <ul>
                                      <li :key="error" v-for="error in errors">{{ error }}</li>
                                    </ul>
                                    </p>
                                  </div>
                                </message-box>
                              </div>
                              <div class="col-2">
                                <img class="hidden-sm-down" width="46" src="@/assets/images/logo-small.png" alt="">
                              </div>
                            </div>
                          </div>
                        </form>
                        <div v-else>
                          <div class="container">
                            <div class="row">
                              <div class="col-md-10">
                                <message-box color="form-blue">
                                  <span v-html="textWithData"></span>
                                </message-box>
                              </div>
                            </div>
                          </div>
                          <div class="container">
                            <div class="row">
                            <div class="col-10">
                              <message-box color="pink">
                                {{ message }}
                              </message-box>
                            </div>
                            <div class="col-2">
                              <img class="hidden-sm-down" width="46" src="@/assets/images/logo-small.png" alt="">
                            </div>
                          </div>
                          </div>
                        </div>
                      </div>
                      <div class="col-md-4 col-xl-3">
                        <ul class="contact-icons text-center list-unstyled">
                          <li>
                            <i class="fas fa-map-marker-alt fa-2x pink-text"></i>
                            <p>
                              Rua Capitão Antônio Rosa, 376, cj. 101, Pinheiros, São Paulo–SP, CEP 01443-010
                            </p>
                          </li>
                          <li>
                            <i class="fas fa-phone fa-2x pink-text"></i>
                            <p>(11) 93751-7265</p>
                            <p>De segunda a sexta das 9h às 19h.</p>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </section>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<script>

import fetchApi from "@/fetch.js";
import MessageBox from "@/components/MessageBox";
export default {
  name: "Home",
  components: {
    MessageBox
  },
  data() {
    return {
      errors: [],
      showForm: true,
      textWithData:String,
      message:String,
      contact_name: null,
      contact_email: null,
      contact_subject: null,
      contact_telephone: null,
      contact_message: null,
      contact_attachment: null
    }
  },
  methods: {
    //verifica se todos os inputs estão preenchidos
    checkForm: function () {
      this.errors = [];

      if (!this.contact_name) {
        this.errors.push('O nome é obrigatório.');
      }
      if (!this.contact_message) {
        this.errors.push('A mensagem é obrigatório.');
      }
      if (!this.contact_subject) {
        this.errors.push('O assunto é obrigatório.');
      }
      if (!this.contact_telephone) {
        this.errors.push('O telefone é obrigatório.');
      }
      if (!this.contact_attachment) {
        this.errors.push('O arquivo é obrigatório.');
      }
      if (!this.contact_email) {
        this.errors.push('O email é obrigatório.');
      } else if (!this.validEmail(this.contact_email)) {
        this.errors.push('Utilize um email válido.');
      }

      if (!this.errors.length) {
        this.sendContact()
      }
    },
    //valida se o email é valido
    validEmail: function (email) {
      var re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      return re.test(email);
    },
    //valida se o arquivo tem menos de 500Kb
    validFileSize: function (file) {
      if (file.files[0].size > 500000) {
        this.errors.push('O arquivo pode ter o tamanho de até 500kb.');
        file.value = null;
        return false;
      }
    },
    //verifica o arquivo no momento de seleção
    handleFileUpload() {
      this.contact_attachment = this.$refs.file.files[0];
      this.validFileSize(this.$refs.file);
    },
    //envia o contato para api
    sendContact() {
      //melhor forma de encapsular quando tem que subir arquivos
      let formData = new FormData();
      formData.set('contact_name', this.$data.contact_name);
      formData.set('contact_email', this.$data.contact_email);
      formData.set('contact_subject', this.$data.contact_subject);
      formData.set('contact_telephone', this.$data.contact_telephone);
      formData.set('contact_message', this.$data.contact_message);
      formData.set('contact_attachment', this.$data.contact_attachment, this.$data.contact_attachment.filename);
      fetchApi.post('/contactsReceived', formData)
          .then((response) => {
            if (response.status == 201) {
              this.errors = [];
              this.showForm = false;
              this.textWithData = "Olá, meu nome é <b>" + this.contact_name + "</b> e o objetivo do meu contato é <b>"+ this.contact_subject + "</b>.<br> <blockquote><i>" + this.contact_message +"</i></blockquote><br> obrigado pela atenção e você pode me responder pelo meu email <b>" + this.contact_email +"</b> ou me ligando no número <b>" + this.contact_telephone + "</b>.";
              this.message = response.data.message;
            }else{
              alert('status:'+response.status + 'Mensagem:'+response.message);
            }
          })
          .catch((error) => {
            alert(error.message);
          });
    },

  }
}
</script>
