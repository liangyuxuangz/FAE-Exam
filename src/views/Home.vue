<template>
	<div class="home">
		<!--    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
		<el-container>
			<el-header>
				<!-- Header -->松下机电FAE 考试系统
			</el-header>
			<el-main>
				<!-- Main -->
				<el-row>
					<el-col :span="2" >
						<div class="grid-content bg-purple" style="background-color: #DCDFE6;">
							<el-button type="text" icon="el-icon-arrow-left" style="background-color: #DCDFE6;line-height: 550px;">上一题</el-button>
						</div>
					</el-col>
					<el-col :span="20">
						<div class="grid-content bg-purple-light" style="background-color: white;"></div>
					</el-col>
					<el-col :span="2">
						<div class="grid-content bg-purple" style="background-color: #DCDFE6;">
							<el-button type="text" icon="el-icon-arrow-right" style="background-color: #DCDFE6;line-height: 550px;">下一题</el-button>
						</div>
					</el-col>
				</el-row>
			</el-main>
			<el-footer height="30px">
				<!-- Footer -->
			</el-footer>
		</el-container>

	</div>
</template>

<script>
	// @ is an alias to /src
	// import HelloWorld from '@/components/HelloWorld.vue'

	export default {
		name: 'home',
		components: {
			// HelloWorld
		}
	}
</script>

<style>
	.el-header {
		background-color: #0099ff;
		color: white;
		text-align: center;
		line-height: 60px;
		font-family:"microsoft yahei";
		font-size: 30px;
		
	}

	.el-footer {
		background-color: #999999;
		color: #333;
		text-align: center;
		line-height: 60px;
	}

	.el-main {
		background-color: #ffffff;
		color: #333;
		text-align: center;
		line-height: 160px;
	}

	.bg-purple {
		background: #d3dce6;
	}

	.bg-purple-light {
		background: #e5e9f2;
	}

	.grid-content {
		border-radius: 0px;
		height: 580px;
		/* min-height: 36px; */
	}

	.el-row {
		margin-bottom: 20px;

		&:last-child {
			margin-bottom: 0;
		}
	}

	.el-col {
		border-radius: 0px;
	}
</style>
