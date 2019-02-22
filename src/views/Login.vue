<template>
	<div class="login">
		<!-- <img src="./assets/panasonic.PNG" /> -->
		<img src="../assets/logo.png" />
		<div class="inputext">
			<el-form :model="Loginform" status-icon :rules="rules2" ref="Loginform" label-width="100px" class="demo-ruleForm">
				<el-form-item label="用户名" prop="username" class="inputext">
					<el-input v-model.number="Loginform.username"></el-input>
				</el-form-item>
				<el-form-item label="密码" prop="pass" class="inputext">
					<el-input type="password" v-model="Loginform.pass" autocomplete="off"></el-input>
				</el-form-item>
				<el-form-item label="确认密码" prop="checkPass" class="inputext">
					<el-input type="password" v-model="Loginform.checkPass" autocomplete="off"></el-input>
				</el-form-item>
				<el-form-item>
					<el-button type="primary" @click="submitForm('Loginform')">提交</el-button>
					<el-button @click="resetForm('Loginform')">重置</el-button>
				</el-form-item>
			</el-form>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'login',
		components: {},
		data() {
			var checkName = (rule, value, callback) => {
				if (!value) {
					return callback(new Error('用户名不能为空'));
				}
				setTimeout(() => {
					// 					if (!Number.isInteger(value)) {
					// 						callback(new Error('请输入用户名'));
					// 					} else {
					// 						if (value < 18) {
					// 							callback(new Error('必须年满18岁'));
					// 						} else {
					// 							callback();
					// 						}
					// 					}
				}, 1000);
			};
			var validatePass = (rule, value, callback) => {
				if (value === '') {
					callback(new Error('请输入密码'));
				} else {
					if (this.ruleForm2.checkPass !== '') {
						this.$refs.ruleForm2.validateField('checkPass');
					}
					callback();
				}
			};
			var validatePass2 = (rule, value, callback) => {
				if (value === '') {
					callback(new Error('请再次输入密码'));
				} else if (value !== this.ruleForm2.pass) {
					callback(new Error('两次输入密码不一致!'));
				} else {
					callback();
				}
			};
			return {
				Loginform: {
					pass: '',
					checkPass: '',
					username: ''
				},
				rules2: {
					pass: [{
						validator: validatePass,
						trigger: 'blur'
					}],
					checkPass: [{
						validator: validatePass2,
						trigger: 'blur'
					}],
					username: [{
						validator: checkName,
						trigger: 'blur'
					}]
				}
			};
		},
		methods: {
			submitForm(formName) {
				this.$refs[formName].validate((valid) => {
					if (valid) {
						alert('submit!');
					} else {
						console.log('error submit!!');
						return false;
					}
				});
			},
			resetForm(formName) {
				this.$refs[formName].resetFields();
			}
		}
	}
</script>

<style>
	.login {
		margin: auto;
		width: 40%;
		/* border: 3px solid #73AD21; */
		padding: 10px;
	}
</style>
