<template>
  <form 
    name="contact_form"
    method="post"
    v-on:submit.prevent="validateBeforeSubmit"
    action="/success/"
    data-netlify="true"
    data-netlify-honeypot="bot-field"
    class="form"
  >
  <p class="slogan">{{slogan}}</p>
  <input type="hidden" name="form-name" value="contact" />
  <p hidden>
    <label>
      Don’t fill this out: <input name="bot-field" />
    </label>
  </p>
    <div class="input-group">
      <label for="business_name" class="label" >Business Name</label>
      <input type="text" name="business_name" v-model="formData.business_name" :class="{'input-error': error && formData.business_name == null}" @change="error = false"/>
    </div>
    <div class="input-group">
      <label for="first_name" class="label" >First Name</label>
      <input type="text" name="first_name" v-model="formData.first_name" :class="{'input-error': error && formData.first_name == null}" @change="error = false"/>
    </div>
    <div class="input-group">
      <label for="last_name" class="label" >Last Name</label>
      <input type="text" name="last_name" v-model="formData.last_name" :class="{'input-error': error && formData.last_name == null}" @change="error = false"/>
    </div>
    <div class="input-group">
      <label for="email">Email</label>
      <input type="email" name="email" v-model="formData.email" :class="{'input-error': error && formData.email == null}" @change="error = false"/>
    </div>
    <div class="input-group">
      <label for="phone">Phone Number</label>
       <input type="text" name="phone" v-model="formData.phone" :class="{'input-error': error && formData.phone == null}" @change="error = false"/>
      <!-- <NumberInput type="text" name="phone" v-model="formData.phone" :class="{'input-error': error && formData.phone == null}" @change="error = false" mask-type="number"/> -->
    </div>
  <button type="submit" class="form-btn" :disabled="sending">
    <span v-if="!sending">Submit</span>
    <span v-if="sending">Submiting...</span>
  </button>


</form>
</template>

<script>

export default {
  name: 'Form',
  props: ['slogan'],
  data() {
    return {
      formData: {
        business_name: null,
        first_name: null,
        last_name: null,
        email: null,
        phone: null
      },
      success: false,
      error: false,
      sending: false
    }
  },
 methods: {
  validateBeforeSubmit(e) {
    for( var key in this.formData) {
      if(this.formData[key] == null || this.formData[key] == '') {
        this.error = true
        return
      }
    }
    this.handleSubmit(e)
  },
  encode(data) {
    return Object.keys(data)
      .map(key => encodeURIComponent(key) + '=' + encodeURIComponent(data[key]))
      .join('&')
  },
  handleSubmit(e) {
    this.sending = true
    fetch('/', {
      method: 'POST',
      headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
      body: this.encode({
        'form-name': e.target.getAttribute('name'),
        ...this.formData,
      }),
    })
    .then(() => {
      this.sending = false
      this.formData = ""
      this.$router.push('/')
      this.success = true
      window.scrollTo(0,0)
    })
    .catch(error => alert(error))
  },
  removeModal() {
    this.success = false
  }
}
}
</script>

<style>
  .success-modal {
    position: absolute;
    top:0;
    left: 0;
  }

  .form {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 500px;
    box-shadow: 0 2px 15px 8px rgba(0, 0, 0, 0.164); 
    padding: 15px;
    border-radius: 3px;
    background: var(--white);
  }

  .hidden {
    display: none;
  }

  input {
    padding: 10px;
    border: .5px solid #b4b4b4;
    border-radius: 3px;
    margin-bottom: 10px;
    font-size: 1.1rem;
    width: 100%;
  }

  .form-btn {
    padding: 10px;
    background: var(--main);
    color: white;
    font-weight: bold;
    font-size: 1.25rem;
    border: none;
    border-radius: 3px;
    width: 100%;
    cursor: pointer;
    box-shadow: 0 0 5px 0 rgba(0,0,0,.25)
  }

  .slogan {
    font-size: 1.5rem;
    font-weight: bold;
    margin-bottom: 10px;
    margin-top: 0;
  }

  .input-error {
    border: 1px solid red!important;
  }

  .input-group {
    width: 100%;
    color: var(--dark);
  }

  @media screen and (max-width: 950px) {
      .form {
          max-width: 400px;
      }
  }

  @media screen and (max-width: 767px) {
    .slogan {
      font-size: 1rem;
    }
  }

  @media screen and (max-width: 458px) {
    .form {
      width: 90%;
    }
  }
</style>

