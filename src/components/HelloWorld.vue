<template>
  <form id="form" @submit.prevent="submit">
      <div>
        <table>
          <tbody>
          <tr>
            <th>ID<b>*</b></th>
            <td>
              <input  type="text" id='userId' name="userId">
            </td>
            <td></td>
          </tr>
          <tr>
            <th>PW</th>
            <td>
              <input type="text" id='userPwd' name="userPwd">
            </td>
            <td></td>
          </tr>
          </tbody>
          <button type="submit">등록</button>
        </table>
      </div>
  </form>
</template>

<script>
export default {
  methods : {
    submit : function () {
      let form = document.getElementById('form')
      let formData = new FormData(form)
      this.$http.post(this.$apiHost + '/user/login', formData)
        .then(function (val) {
          alert(val)
          console.log(val)
        })
    }
  }
}
</script>
]
