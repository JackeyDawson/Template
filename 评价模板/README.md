### 打分发布评价模板使用说明
#### 当前版本：<span style="color:red">1.0.0</span>

#### 引入
``` javascript
	import myIssue from '@/components/myIssue.vue'
	export default {
		components: {myIssue}
	}
```

#### 使用

基本使用
``` 
	<my-issue />
```

设置初始分值
```
	<my-issue :score="3" />
```

不可修改分数
```
	<my-issue :starsDisabled="true" />
```
另外组合自行测试

#### 参数说明

<table cellpadding="5"  style="font-size:16px;width:100%">
	<tr>
		<th>参数名称</th>
		<th>是否必须</th>
		<th>默认值</th>
		<th>说明</th>
	</tr>
	<tr>
		<td>headPicShow</td>
		<td>否</td>
		<td>true</td>
		<td>头像显示</td>
	</tr>
	<tr>
		<td>headPicValue</td>
		<td>否</td>
		<td></td>
		<td>头像</td>
	</tr>
	<tr>
		<td>headTitleShow</td>
		<td>否</td>
		<td>true</td>
		<td>标题显示</td>
	</tr>
	<tr>
		<td>headTitleValue</td>
		<td>否</td>
		<td></td>
		<td>标题</td>
	</tr>
	<tr>
		<td>starsShow</td>
		<td>否</td>
		<td>true</td>
		<td>星星显示</td>
	</tr>
	<tr>
		<td>starsMax</td>
		<td>否</td>
		<td>5</td>
		<td>星星最大个数</td>
	</tr>
	<tr>
		<td>starDefault</td>
		<td>否</td>
		<td></td>
		<td>星星默认图片</td>
	</tr>
	<tr>
		<td>starActive</td>
		<td>否</td>
		<td></td>
		<td>星星选中图片</td>
	</tr>
	<tr>
		<td>score</td>
		<td>否</td>
		<td>0</td>
		<td>默认分数</td>
	</tr>
	<tr>
		<td>starsDisabled</td>
		<td>否</td>
		<td>false</td>
		<td>星星禁用</td>
	</tr>
	<tr>
		<td>textareaShow</td>
		<td>否</td>
		<td>true</td>
		<td>多行文本显示</td>
	</tr>
	<tr>
		<td>textareaPlaceholder</td>
		<td>否</td>
		<td></td>
		<td>多行文本placeholder</td>
	</tr>
	<tr>
		<td>submitShow</td>
		<td>否</td>
		<td>true</td>
		<td>按钮显示</td>
	</tr>
	<tr>
		<td>submitText</td>
		<td>否</td>
		<td>发布</td>
		<td>按钮文本</td>
	</tr>
	<tr style="color:red">
		<td>infoReceive</td>
		<td>否</td>
		<td>{score:0,textareaValue:""}</td>
		<td>打分和评论（可以不传，传必须完整）</td>
	</tr>
</table>


#### 插槽使用
``` js 
头像插槽：slot="headPic"
<my-issue> <image slot="headPic"></image> </my-issue>

按钮插槽：slot="submit"，同上。

```

#### 事件监听
<table cellpadding="5"  style="font-size:16px;width:100%">
	<tr>
		<th>参数名</th>
		<th>是否必传</th>
		<th>说明</th>
	</tr>
	<tr>
		<td>@submit</td>
		<td>否</td>
		<td>this.$emit('submit',{分数+评论})</td>
	</tr>
	<tr>
		<td>@scoreChange</td>
		<td>否</td>
		<td>this.$emit('scoreChange',分值)</td>
	</tr>
</table>