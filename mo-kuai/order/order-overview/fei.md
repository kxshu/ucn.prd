# Order Overview（以采购商端为例，供应商端参考，服务商端无）

## 定义

Order Overview页面即对历史订单的总览，主要解决`订单进度跟踪`和`订单查找`功能，并可切换浏览方式`产品或者订单`

相关模块如下：

| 板块 | 备注 |
| :--- | :--- |
| 顶部导航 | 无二级菜单 |
| 侧边栏 |  |
| 状态栏及对应的操作 |  |
| 搜索栏及对应的浏览方式和明细 |  |

## 完整字段：

[Order Overview字段](https://shimo.im/sheet/xfd3j2LGNQsQ3q65/nrxCR)

## 需求说明

### 侧边栏

##### Quick Link

默认Inquiry Overview、Order Overview、Warehouse Overview、Logistics Plan Overview，以及Add Link，每个快捷链接可移除

##### Pages

Draft（？）：？代表Order模块的草稿数，点击新页签打开

Recycle Bin（？）：？代表Order模块的回收数，点击新页签打开

##### Actions

Create Order：点击新页签打开[create order](/mo-kuai/order/create-order.md)页面

Download the Overview ：所有Order不加筛选条件导出，弹出下载面板，导出模板见[Order导出模板](https://shimo.im/sheet/xfd3j2LGNQsQ3q65/pvncg)

### 状态栏及对应的操作

本模块展现所有订单对应的阶段状态，在不同阶段的订单有相应操作，可单一或批量

##### **供应商端的说明：**

状态参考采购商端，但把customer和supplier文案对调

1. ##### TBC by customer规则如下：

   | 操作按钮 | 可否点击 | 可否批量操作 | 点击后的效果 | 跳转 |
   | :--- | :--- | :--- | :--- | :--- |
   | Download Selected（？） | Y | Y | 弹出面板框下载勾选项 | N |
   | Accept | Y | Y | 使勾选的订单进入Procecss阶段 | N |
   | Copy | Y | N | 复制勾选的单个订单成为一个新订单，不带history | 新页签跳转到create order界面 |
   | Cancle | Y | Y | 点击后使勾选的订单进入Cancled阶段 | N |
   | Delete | N | N | Null | N |
2. ##### TBC by supplier规则如下：

   | 操作按钮 | 可否点击 | 可否批量操作 | 点击后的效果 | 跳转 |
   | :--- | :--- | :--- | :--- | :--- |
   | Download Selected（？） | 同1 |  |  |  |
   | Accept | N | N | Null | N |
   | Copy | 同1 |  |  |  |
   | Cancle | 同1 |  |  |  |
   | Delete | 同1 |  |  |  |
3. ##### Procecss规则如下：

   | 操作按钮 | 可否点击 | 可否批量操作 | 点击后的效果 | 跳转 |
   | :--- | :--- | :--- | :--- | :--- |
   | Download Selected（？） |  |  |  |  |
   | Accept | 同2 |  |  |  |
   | Copy | 同1 |  |  |  |
   | Cancle | 同1 |  |  |  |
   | Delete | 同1 |  |  |  |
   | Finish | Y | Y | 勾选项进入Finished | N |

   ##### 阶段说明：

   Order 进入“Process”阶段的标志是：购、销任意一方点击确认；人工手动Finish的，依然可以再次进入TBC

4. ##### Finished规则如下

   | 操作按钮 | 可否点击 | 可否批量操作 | 点击后的效果 | 跳转 |
   | :--- | :--- | :--- | :--- | :--- |
   | Download Selected（？） |  |  |  |  |
   | Accept | 同2 |  |  |  |
   | Copy | 同1 |  |  |  |
   | Cancle | N | N | Null | N |
   | Delete | Y | Y | 进入操作方的Recycle Bin | N |

   ##### 阶段说明：

   Order 进入“Finish”阶段的标志是：按照价格条款，如果是EXW，验货确认视为finish；如果是FOB，on board date视为finish；如果是CIF，到港日期视为finish；Order可以从Finished再次进入TBC

5. ##### Cancled规则如下：

   | 操作按钮 | 可否点击 | 可否批量操作 | 点击后的效果 | 跳转 |
   | :--- | :--- | :--- | :--- | :--- |
   | Download Selected（？） |  |  |  |  |
   | Accept | 同2 |  |  |  |
   | Copy | 同1 |  |  |  |
   | Cancle | 同4 |  |  |  |
   | Delete | 同4 |  |  |  |

### 搜索栏及对应的浏览方式和明细

本模块根据用户的搜索内容和浏览方式，判断明细表呈现的维度

搜索方式：Order No., SKU Code

浏览方式：Order, SKU（[overview by 字段](https://shimo.im/sheet/xfd3j2LGNQsQ3q65/nrxCR )）

##### 



