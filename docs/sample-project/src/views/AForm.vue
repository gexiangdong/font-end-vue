<template>
  <div>
    <h1>
      表单的例子
      <p class="page-desc">页面底部有背景色的区域显示了页面Data()中的数据，因为Data()中数据和表单双向绑定，所以表单中修改会在底部实时更新。</p>
    </h1>
    <form>
      <div>姓名：</div>
      <div><input type="text" autofocus="autofocus" v-model="name" /></div>

      <div>性别：</div>
      <div>
        <input type="radio" id="gender-male" name="gender" value="男" v-model="gender" /><label for="gender-male">男</label>
        <input type="radio" id="gender-female" name="gender" value="女" v-model="gender" /><label for="gender-female">女</label>
      </div>

      <div>来自：</div>
      <div>
        <select v-model="province">
          <option value="北京">北京</option>
          <option value="上海">上海</option>
          <option value="广州">广州</option>
          <option value="深圳">深圳</option>
        </select>
      </div>

      <div>简介：</div>
      <div><textarea v-model="intro"></textarea></div>

      <div>爱好：</div>
      <div>
        <input type="checkbox" value="吃" id="chi" v-model="hobbies" /><label for="chi">吃</label>
        <input type="checkbox" value="喝" id="he" v-model="hobbies" /><label for="he">喝</label>
        <input type="checkbox" value="玩" id="wan" v-model="hobbies" /><label for="wan">玩</label>
        <input type="checkbox" value="乐" id="le" v-model="hobbies" /><label for="le">乐</label>
      </div>

      <div></div>
      <div><input type="checkbox" id="iagreewithite" v-model="agree"><label for="iagreewithite">我同意注册协议……</label></div>

      <div></div>
      <div><button v-on:click="submitForm">提交</button></div>
    </form>

    <div class="display">
      <div>姓名：{{name}}</div>
      <div>性别：{{gender}}</div>
      <div>来自：{{province}}</div>
      <div>简介：{{intro}}</div>
      <div>爱好：{{hobbies}}</div>
      <div>是否同意注册协议：{{agree}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Form',
  data() {
    return {
      name: null,
      gender: null,
      intro: null,
      province: '上海',
      hobbies: [],
      agree: false
    }
  },
  methods:{
    submitForm: function(){
      console.log("submitForm")
    }
  }
}
</script>

<style scoped>
form {display: grid; grid-template-columns: 50px auto; grid-row-gap:20px; text-align: left; width: 600px; }
input[type=text] {width: 500px;}
textarea{width: 500px; height: 50px;}

.display{width: 500px; background-color: #F7F7F7; border-radius:5px; border:1px dotted #999; padding: 15px 20px; margin: 40px 0; text-align: left;}
</style>
