### 什么是表格：

表格是由**行和列**组成的**结构化数据集**\(表格数据\)，它能够使你简捷迅速地查找某个表示不同类型数据之间的某种关系的值 。

### 如何创建表格：

```html
<table>    表格
<caption></caption> 表头
<thead>表格头(用来写项目名称)
    <tr>
        <th></th>  表格标题
    </tr>
</thead>  
<tr>       行
<td></td> 列
<td></td>
<td></td>
</tr>
<tfoot>
    <tr>
        <td>
        </td>
        <td>
        </td>
    </tr>
</tfoot> 表尾(最后一行的总结行)
</table>
```

### 表格基本操作

#### 表格的属性

| 属性 | 含义 |
| :---: | :---: |
| border | 边框\(宽度\) |
| width | 宽度 |
| height | 高度 |
| cellspacing | 单元格之间的距离 |
| cellpadding | 内容距边框的距离 |
| align | 给表格用表格居中，给tr或td，则tr或td内容居中 |
| bgcolor | 背景颜色，可以给某个单元格使用 |

#### 单元格合并

```html
<td colspan=”2”></td>  合并同一行上的单元格
<td rowspan=”2”></td>  合并同一列上的单元格
```

#### 边框颜色：

```html
<table bordercolor="red"></table>
```

#### 内容竖直方向对齐方式

```html
<tr>
    <td colspan="4" valign="middle">第二人称</td>
    <td colspan="2" valign="bottom">you</td>
    <td colspan="2" valign="top">you</td>
</tr>
```

**valign**取值： `top | middle | bottom`

#### 内容水平方向对齐方式

```html
<tr>
    <td colspan="4" align="right">第三人称</td>
    <td colspan="2" align="left">they</td>
    <td colspan="2" align="center">them</td>
</tr>
```

**align**取值：`left| right| center`,align如果直接给表格用，表格居中，如果给tr或者td用，tr或者td内容居中

