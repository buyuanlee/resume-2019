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
						<div v-for="blog in blogs" v-bind:key="blog.index" class="item-content">
							<svg class="icon blog-icon item-type" aria-hidden="true">
								<use v-bind:xlink:href="`#icon-${blog.icon}`"></use>
							</svg>
							<div class="line"></div>
							<a class="blog-url" :href="`${blog.url}`" target="_blank">点击访问主页</a>
						</div>
					</div>
				</div>
			</el-col>
			<!--      内容-->
			<el-col :span="16">
				<div class="content">
<!--					个人信息-->
					<div class="about content-item">
						<span class="item-title">技能介绍</span>
						<el-timeline>
							<el-timeline-item timestamp="个人常用技术栈" placement="top">
							<el-card class="card">
								<ul>
									<li>精通 <span class="highlight">css3、html5、JavaScript</span> 基本前端语法</li>
									<li>熟悉<span class="highlight">es6</span>常用语法/可以使用<span class="highlight">SASS</span>开发</li>
									<li>熟悉vue全家桶及其使用，可以利用<span class="highlight">Vue</span>全家桶+<span class="highlight">ElementUI</span>进行快速开发</li>
									<li>熟悉<span class="highlight">小程序</span>开发流程，有小程序的开发经验</li>
									<li>熟悉<span class="highlight">H5页面</span>的开发，使用过微信的常用接口</li>
								</ul>
							</el-card>
							</el-timeline-item>
						</el-timeline>
					</div>
<!--					工作经历-->
					<div class="job content-item">
						<span class="item-title">工作经历</span>
						<el-timeline>
							<el-timeline-item timestamp="2018/08/01-2019/08/15" placement="top">
								<el-card class="card">
									<h4>公司名称</h4>
									<span>杭州去打球文化创意有限公司</span>
									<h4>工作职责</h4>
									<span>主要负责公司的web端业务、微信小程序与微信H5相关页面</span><br>
									<span>1.从搭建到上线，全程参与公司的商家后台管理系统的业务</span><br>
									<span>2.公司小程序纹乐Tattoofun的业务</span><br>
									<span>3.辅助APP开发人员内嵌H5页面</span><br>
									<span>4.公司营销相关的H5页面</span>
								</el-card>
							</el-timeline-item>
						</el-timeline>
					</div>
<!--					项目经历-->
					<div class="project content-item">
						<span class="item-title">项目经历</span>
						<el-timeline>
<!--							后台管理系统-->
							<el-timeline-item timestamp="SAAS商家后台管理系统" placement="top">
								<el-card class="card">
									<h4>项目介绍</h4>
									<p>此项目是给入驻平台商家使用的后台管理系统，前端使用的是Vue，后端使用的是Java。
										主要功能有店铺数据查看、店铺基本信息修改、人员管理、顾客管理、店铺装修、优惠券管理、作品管理。
										我从项目搭建开始负责，参与了项目的需求讨论，前端的代码规范制定以及落地执行，该项目目前已上线。
									</p>
									<h4>项目技术栈</h4>
									<span>项目使用 <b class="highlight">Vue-Cli3</b>搭建</span><br>
									<span>UI组件使用<b class="highlight">ElementUI</b>进行快速开发</span><br>
									<span>项目样式使用<b class="highlight">SASS</b>进行开发</span><br>
									<span>使用<b class="highlight">Vuex</b>进行状态管理</span><br>
									<span>使用<b class="highlight">Vue-Router</b>进行路由管理，使用的是hash模式</span><br>
									<span>使用的第三方库有 <b class="highlight">V-charts、Axios、QS、Baidu-Map</b></span>
									<h4>相关链接</h4>
									<a href="https://www.wenleapp.com/businessBack" target="_blank"><b class="highlight">点击进入线上地址</b></a>
								</el-card>
							</el-timeline-item>
<!--							微信小程序-->
							<el-timeline-item timestamp="微信小程序" placement="top">
								<el-card class="card">
									<h4>项目介绍</h4>
									<p>此项目是公司的官方微信小程序，主要功能移植了APP端的图库、圈子、以及个人信息的功能。
										使用者可以在此小程序上使用查看纹身图片，查找纹身商家，以及参与圈子互动等功能。
									</p>
									<h4>项目技术栈</h4>
									<span>项目使用微信小程序原生框架开发</span><br>
									<span>登陆功能使用微信云函数的<b class="highlight">微信授权</b></span><br>
									<span>JS部分使用了<b class="highlight">ES6</b>相关语法</span><br>
									<span>图库采用瀑布流组件多次复用</span><br>
									<h4>相关链接</h4>
									<span>微信搜索小程序：</span><b class="highlight">纹乐Tattoofun</b>
								</el-card>
							</el-timeline-item>
<!--							UI组件-->
							<el-timeline-item timestamp="UI组件库" placement="top">
								<el-card class="card">
									<h4>项目介绍</h4>
									<p>此项目是个人开源项目，是参考ElementUI重写的开源UI组件库，
										现有组件包括Button、Icon、ButtonGroup、Input、Layout,其余组件仍在更新中。
										目前该项目已发布npm包，但尚不可以用于生产环境。
									</p>
									<h4>项目技术栈</h4>
									<span>项目使用<b class="highlight">Vue-cli3</b>进行快速开发</span><br>
									<span>官方文档页面使用<b class="highlight">VuePress</b>搭建</span><br>
									<span>路由使用<b class="highlight">Vue-Router</b>管理</span><br>
									<span>项目样式使用<b class="highlight">SASS</b>开发</span><br>
									<h4>相关链接</h4>
									<a href="https://buyuanlee.github.io/AloeUI/index.html" target="_blank"><b class="highlight">点击预览页面</b></a><br>
									<a href="https://github.com/buyuanlee/AloeUI" target="_blank"><b class="highlight">点击查看源码</b></a>
								</el-card>
							</el-timeline-item>
						</el-timeline>
					</div>
					<!--					自我评价-->
					<div class="about content-item">
						<span class="item-title">自我评价</span>
						<el-timeline>
							<el-timeline-item timestamp="个人常用技术栈" placement="top">
								<el-card class="card">
									<p>兴趣驱动，学习能力强，自我管理能力强，渴望在前端领域更好的发展，享受coding</p>
								</el-card>
							</el-timeline-item>
						</el-timeline>
					</div>
				</div>
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
                    {name: '掘金', icon: 'juejin', url: 'https://juejin.im/user/5b9d2782e51d450e4006a485/posts'},
                    {name: '简书', icon: 'jianshu', url: 'https://www.jianshu.com/u/5362a3ed6b43'},
                ]
            }
        }
    }
</script>

<style scoped lang="scss">
	.icon {
		color: #67b1a0;
	}

	.blog-icon {
		color: #ffffff;
	}

	/*页面*/
	.page {
		color: #7d7d7d;
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
		background: #e9e9e9;
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
		border-bottom: 1px solid #bcbcbc;
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
		background: #bcbcbc;
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
		margin: 12px 0 6px 0;
	}

	/*联系方式*/
	.contact {
		display: flex;
		flex-direction: column;
	}

	.blog {
		background: #67b1a0;
		color: #ffffff;
		display: flex;
		flex-direction: column;
	}

	.blog-url {
		color: #ffffff;
	}

	/*内容*/
	.card{
		font-size: 16px;
		color:#7d7d7d;
		letter-spacing: 2px;
		h4{margin: 8px 0 4px;}
		a{text-decoration: underline;color: #67b1a0}
	}
	.content {
		background: #fff;
		margin-right:30px ;
		padding-top: 12px;
	}
	.content-item{
		text-align: left;
		margin: 24px 36px;
	}
	.item-title{
		display: flex;
		justify-content: center;
		font-size: 36px;
		color: #bcbcbc;
		font-weight: bold;
	}
	.highlight{
		font-weight: bold;
		color: #67b1a0;
	}
</style>
