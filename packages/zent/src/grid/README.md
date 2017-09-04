## Grid 网格

网格组件

### 代码演示

<!-- :::demo 基础用法
```jsx
import { Grid } from 'zent';

const columns = [
	{
		title: '商品名',
		name: 'name'
	}, {
		title: '访问量',
		name: 'uv'
	}, {
		title: '库存',
		name: 'stock'
	}
];

const datasets = [];

for (let i = 0; i < 3; i++) {
	datasets.push({
		name: `商品 ${i}`,
		uv: 20,
		stock: 5
	})
}

ReactDOM.render(
		<Grid
			columns={columns}
			datasets={datasets}
		/>
	, mountNode
);

```
:::


:::demo 加载
```jsx

import { Grid } from 'zent';

const columns = [
	{
		title: '商品名',
		name: 'name'
	}, {
		title: '访问量',
		name: 'uv'
	}, {
		title: '库存',
		name: 'stock'
	}
];

const datasets = [];

for (let i = 0; i < 3; i++) {
	datasets.push({
		name: `商品 ${i}`,
		uv: 20,
		stock: 5
	})
}

class Loading extends React.Component {
	render() {
		return (
			<Grid
				columns={columns}
				datasets={datasets}
				loading
			/>
		);
	}
};

ReactDOM.render(
		<Loading />
	, mountNode
);

```
:::


:::demo 分页
```jsx

import { Grid } from 'zent';

const columns = [
	{
		title: '商品名',
		name: 'name'
	}, {
		title: '访问量',
		name: 'uv'
	}, {
		title: '库存',
		name: 'stock'
	}
];

const datasets = [];

for (let i = 0; i < 3; i++) {
	datasets.push({
		name: `商品 ${i}`,
		uv: 20,
		stock: 5
	})
}

const pageSize = 5;
const totalItem = 50;

class PageInfo extends React.Component {
	state = {
		current: 1
	}

	onChange = ({ current }) => {
		console.log(current, 'current');
		this.setState({
			current: current
		})
	}

	render() {
		return (
			<Grid
				columns={columns}
				datasets={datasets}
				pageInfo={{
					current: this.state.current,
					pageSize: pageSize,
					totalItem: totalItem
				}}
				onChange={this.onChange}
			/>
		);
	}
};

ReactDOM.render(
		<PageInfo />
	, mountNode
);

```
:::
 -->

:::demo colSpan & rowSpan
```jsx

import { Grid } from 'zent';

const columns = [
	{
		title: '商品名',
		name: 'name',
		colSpan: 2,
		bodyRender: (data, pos) => {
			if (pos.row === 1) {
				return <span>{data.name}</span>
			}

			return {
				props: {
					colSpan: 2
				},
				children: <span>{data.name}</span>
			}
		}
	}, {
		title: '访问量',
		name: 'uv'
	}, {
		title: '库存',
		name: 'stock'
	}
];

const datasets = [];

for (let i = 0; i < 20; i++) {
	datasets.push({
		name: `商品 ${i}`,
		uv: 20,
		stock: 5
	})
}

class Span extends React.Component {
	render() {
		return (
			<Grid
				columns={columns}
				datasets={datasets}
			/>
		);
	}
};

ReactDOM.render(
		<Span />
	, mountNode
);

```
:::