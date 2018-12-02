<template>
	<div>
		<Table stripe :columns="columns1" :data="data1"></Table>
	</div>

</template>
<script>
	export default {
		data() {
			return {
				columns1: [{
						title: '序号',
						key: 'id',
						sortable: true
					},
					{
						title: '标题',
						key: 'title'
					},
					{
						title: '地址',
						key: 'address',
						render: (h, params) => {
							//return h('定义的元素', {'元素的性质'}, '元素的内容');
							return h('a', {
								attrs: {
									href: params.row.address,
									target: '_black'
								}
							}, params.row.address)
						}
					},
					{
						title: '日期',
						key: 'date',
						sortable: true
					}
				],
				data1: [{
						id: 1,
						title: "博客园",
						address: 'https://www.cnblogs.com/oukele',
						date: '2018-8-18'
					},
					{
						id:2,
						title:'HTML 获取class里的多个值 和 dataset的使用',
						address:'https://www.cnblogs.com/oukele/p/9516743.html',
						date:'2018-8-22'
					},
					{
						id:3,
						title:'HomeWork',
						address:'https://github.com/oukele/homework-ouyile',
						date:'2018-8-22'
					},
					{
						id:4,
						title:'利用Mybatis-generator根据数据库生成相关文件的简单demo',
						address:'https://github.com/oukele/distribution',
						date:'2018-9-1'
					},
					{
						id:5,
						title:'swagger_demo',
						address:'https://github.com/oukele/swagger_demo',
						date:'2018-10-30'
					},
					{
						id:6,
						title:'简单的知乎App',
						address:'https://github.com/oukele/Fang_zhihu',
						date:'2018-11-15'
					},
					{
						id:7,
						title:'HomeWork_01',
						address:'https://github.com/oukele/HomeWork',
						date:'2018-9-10'
					},
					{
						id:8,
						title:'Vue + 实现 简单任务管理',
						address:'https://github.com/oukele/Vue-task-todo',
						date:'2018-12-1'
					}
				]
			}
		}
	}
</script>
