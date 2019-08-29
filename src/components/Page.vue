<template>
	<!--  页面-->
	<div class="page">
		<!--    头部-->
		<div class="head">
			<h2 class="name">李建伟</h2>
			<span class="job">WEB前端开发</span>
		</div>
		<!--    主要-->
		<el-row class="main">
			<!--      侧边-->
			<el-col :span="8">
				<div class="aside">
					<!--					头像-->
					<div class="avatar aside-item">
						<el-avatar class="avatarImg" :size="150" :src="avatarUrl" fit="cover"></el-avatar>
					</div>
					<!--					基本信息-->
					<div class="info aside-item">
						<span class="title">基本信息</span>
						<ul>
							<li v-for="info in infos" v-bind:key="info.index" class="item-content">
								<svg class="icon item-type" aria-hidden="true">
									<use v-bind:xlink:href="`#icon-${info.type}`"></use>
								</svg>
								<div class="line"></div>
								<span class="item-value">{{info.value}}</span>
							</li>
						</ul>
					</div>
					<!--					技能-->
					<div class="skill aside-item">
						<span class="title">专业技能</span>
						<div v-for="skill in skills" v-bind:key="skill.index">
							<span class="skill-name">{{skill.name}}</span>
							<el-progress :percentage="skill.percent" color="#bbb" :stroke-width="12" :show-text=false></el-progress>
						</div>
					</div>
					<!--					联系方式-->
					<div class="contact aside-item">
						<span class="title">联系方式</span>
						<ul>
							<li v-for="contact in contacts" v-bind:key="contact.index" class="item-content">
								<svg class="icon item-type" aria-hidden="true">
									<use v-bind:xlink:href="`#icon-${contact.type}`"></use>
								</svg>
								<div class="line"></div>
								<span class="item-value">{{contact.value}}</span>
							</li>
						</ul>
					</div>
					<!--					社交主页-->
					<div class="blog aside-item">
						<span class="title">社交主页</span>
						<div v-for="blog in blogs" v-bind:key="blog.index">
							<svg class="icon blog-icon" aria-hidden="true">
								<use v-bind:xlink:href="`#icon-${blog.icon}`"></use>
							</svg>
						</div>
					</div>
				</div>
			</el-col>
			<!--      内容-->
			<el-col :span="16">
				<div class="content"></div>
			</el-col>
		</el-row>
	</div>
</template>

<script>
    export default {
        name: 'Page',
        data() {
            return {
                avatarUrl: require('../assets/img/avatar.jpg'),
                infos: [{type: 'age', value: '1995'},
                    {type: 'school', value: '安徽大学江淮学院'},
                    {type: 'speciality', value: '电子商务'}],
                contacts: [{type: 'wechat', value: 'buyuanlee'},
                    {type: 'tel', value: '13721052049'},
                    {type: 'email', value: '152927520@qq.com'}],
                skills: [{name: 'HTML5/CSS3/JavaScript', percent: 90},
                    {name: 'Vue/VueRouter/Vuex', percent: 90},
                    {name: '微信小程序', percent: 85},
                    {name: 'NodeJS', percent: 60},],
                blogs: [{name: 'GitHub', icon: 'github', url: 'https://github.com/buyuanlee'},
                    {name: '掘金', icon: 'juejin', url: 'https://github.com/buyuanlee'},
                    {name: '简书', icon: 'jianshu', url: 'https://github.com/buyuanlee'},
                ]
            }
        }
    }
</script>

<style scoped lang="scss">
	.icon {
		color: #67b1a0;
	}

	/*页面*/
	.page {
		color: #717180;
		margin: 24px auto;
		padding: 0 12px;
		max-width: 1240px;
		font-family: "PingFangSC-Regular", "Hiragino Sans GB", "Microsoft YaHei", Arial, sans-serif;
	}

	/*头部*/
	.head {
		display: flex;
		flex-direction: column;
		justify-content: center;
		height: 160px;
		width: 100%;
		background: #353535;
		color: white;

		.name {
			font-size: 36px;
			margin-bottom: 12px;
		}
	}

	/*main*/
	.main {
		height: 200px;
	}

	/*侧边*/
	.aside {
		background: #e9e9e9;
		font-size: 18px;
	}

	.aside-item {
		padding: 24px;
	}

	.title {
		display: inline-block;
		letter-spacing: 4px;
		font-weight: bold;
		margin-bottom: 12px;
	}

	/*头像*/
	.avatar {
		position: relative;
		top: -100px;
	}

	/*基本信息*/
	.info {
		margin-top: -140px;
	}

	.item-content {
		display: flex;
		align-items: center;
		border-bottom: 1px solid #bcbcd3;
		width: 85%;
		line-height: 32px;
	}

	.item-type {
		margin-right: 12px;
	}

	.item-value {
		word-break: break-word;
	}

	.line {
		width: 1px;
		height: 40px;
		background: #bcbcd3;
		margin-right: 12px;
	}

	/*技能*/
	.skill {
		background: #67b1a0;
		color: #ffffff;
		display: flex;
		flex-direction: column;
	}

	.skill-name {
		display: flex;
		margin: 12px 0;
	}

	/*联系方式*/
	.contact {
		display: flex;
		flex-direction: column;
	}

	.blog {
		background: #67b1a0;
		color: #ffffff;
	}

	.blog-icon {
		color: #ffffff;
		width: 2em;
		height: 2em;
	}

	/*内容*/
	.content {
		background: white;
	}
</style>
