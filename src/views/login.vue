<template>
 <v-card>
   <v-row>
     <v-col>
       <v-form
           ref="form"
           v-model="valid"
           lazy-validation
       >
         <v-text-field
             v-model="question"
             :rules="questionRules"
             label="学号"
             required
         ></v-text-field>

         <v-text-field
             v-model="site"
             :rules="siteRules"
             label="密码"
             required
         ></v-text-field>

         <v-select
             v-model="select"
             :items="items"
             :rules="[v => !!v || '该字段必填']"
             label="领域"
             required
         ></v-select>


         <v-btn
             color="success"
             class="mr-14"
             type="submit"
             :disabled="invalid"
         >
           提交
         </v-btn>
         <v-btn
             color="error"
             @click="clear">
           清空
         </v-btn>
       </v-form>
     </v-col>
   </v-row>
 </v-card>
</template>

<script>
export default {
  name: "Submit",
  data: () => ({
    valid: true,
    question: '',
    questionRules: [
      v => !!v || '该字段必填',
    ],
    site: '',
    siteRules: [
      v => !!v || '该字段必填',
    ],
    select: null,
    items: [
      '水',
      '电',
      '网络',
      '电脑',
      '房屋问题',
    ],
    checkbox: false,
  }),

  methods: {
    submit () {
      this.$refs.observer.validate()
    },
    clear () {
      this.name = ''
      this.phoneNumber = ''
      this.email = ''
      this.select = null
      this.checkbox = null
      this.$refs.observer.reset()
    },
  },
}
</script>

<style scoped>

</style>