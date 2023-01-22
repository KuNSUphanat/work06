<template>
  <div class="bg-dark">
    <header>
      <div class="navbar navbar-light bg-light" style="display:flex ;">
        <div class="pic">
          <a class="navbar-brand brand-logo" href="/index.html">
            <img src="src/MJU_LOGO.svg.png" alt="logo"  style="width:50px;height:50px;"/>
          </a>
        </div>
        <div class="container d-flex justify-content-between">
          <a class="navbar-brand d-flex align-items-center" href="#"
            ><i class="fab fa-instagram social-icon"></i><strong>&nbsp;คำร้องขอโอนย้ายสาขาวิชาต่างคณะ สำหรับหลักสูตร 4 ปี และหลักสูตร 4 ปีเทียบเรียน(2ปี)</strong></a>
        </div>
      </div>
    </header>
    
    <div>
      <div class="container">
        <div class="row mt-5">
          <div class="col-md-4">
            <div class="card">
              <div class="card-header">คำร้องขอโอนย้ายสาขาวิชาต่างคณะ</div>
              <div class="card-body">
                <form class="form">
                  <div class="form-group">
                    <label for="date">วัน/เดือน/ปี:</label>
                    <input
                      class="form-control"
                      type="date"
                      v-model="formData.date"
                      id="date"
                    />
                  </div>
                  <div class="form-group">
                    <label for="to">เรียน คณบดีคณะ(คณะใหม่):</label>
                    <input
                      class="form-control"
                      type="text"
                      v-model="formData.to"
                      id="to"
                    />
                  </div>

                  <div class="form-group">
                    <label for="name">ชื่อ-นามสกุล:</label>
                    <input
                      class="form-control"
                      type="text"
                      v-model="formData.name"
                      id="name"
                    />
                  </div>
                  <div class="form-group">
                    <label for="studentID">รหัสนักศึกษา:</label>
                    <input
                      class="form-control"
                      type="text"
                      v-model="formData.studentID"
                      id="studentID"
                    />
                  </div>
                  <div class="form-group">
                    <label for="telephone">โทรศัพท์มือถือ:</label>
                    <input
                      class="form-control"
                      type="text"
                      v-model="formData.telephone"
                      id="telephone"
                      maxlength="10"
                    />
                  </div>
                  <div class="form-group">
                    <label for="major">สาขาวิชา:</label>
                    <input
                      class="form-control"
                      type="text"
                      v-model="formData.major"
                      id="major"
                    />
                  </div>
                  <div class="form-group">
                    <label for="faculty">คณะ:</label>
                    <input
                      class="form-control"
                      type="text"
                      v-model="formData.faculty"
                      id="faculty"
                    />
                  </div>
                  <div class="form-group">
                    <label for="subject">มีความประสงค์จะขอโอนย้ายไปสาขาวิชา:</label>
                    <input
                      class="form-control"
                      type="text"
                      v-model="formData.subject"
                      id="subject"
                    />
                  </div>
                  <div class="form-group">
                    <label for="subject1">เนื่องจาก:</label>
                    <input
                      class="form-control"
                      type="text"
                      v-model="formData.subject1"
                      id="subject1"
                    />
                  </div>
                  <div class="form-group">
                    <label for="email">Email:</label>
                    <input
                      class="form-control"
                      type="email"
                      v-model="formData.email"
                      id="email"
                    />
                  </div>

                  <div class="form-group">
                    <label for="reason">เหตุผลประกอบ:</label>
                    <textarea
                      class="form-control"
                      v-model="formData.reason"
                      id="reason"
                    ></textarea>
                  </div>

                  <button
                    type="submit"
                    class="btn btn-primary"
                    @click.prevent="submitForm"
                  >
                    Submit
                  </button>
                </form>
              </div>
            </div>
          </div>
          <div class="col-md-8">
            <AccordionItems :formDataArray="formDataArray" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import AccordionItems from "./components/AccordionItems.vue";
export default {
  data() {
    return {
      formData: {
        date: null,
        subject: "",
        to: "",
        name: "",
        studentID: "",
        major: "",
        faculty: "",
        telephone: "",
        email: "",
        reason: "",
      },
      formDataArray: [],
    };
  },
  components: {
    AccordionItems,
  },
  methods: {
    submitForm() {
      // Add the form data to the formDataArray
      this.formDataArray.push(this.formData);

      // Reset the formData object
      this.formData = {
        date: null,
        subject: "",
        to: "",
        name: "",
        studentID: "",
        major: "",
        faculty: "",
        telephone: "",
        email: "",
        reason: "",
      };
    },
  },
};
</script>
<style>
.pic{
  margin: 0% 0% 0% 20%;
}
</style>
