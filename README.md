# 灵活用工平台

基于 ThinkPHP+Mysql 灵活用工+灵活用工平台+灵活用工系统+灵活用工小程序+灵活用工源码+灵活用工系统源码·

# 技术架构

开发语言 ThinkPHP+Mysql

# 角色说明

  # 说明
  
   分包商：税地注册公司，用于在当地申请有利的税收政策，是实际报税公司。
  
   代理商：代理商可以邀请客户使用本平台，平台会给予代理商一定的服务费差价作为佣金。
  
   客户：使用本平台进行工资发放的企业。
  
   灵活用工人员：通过本平台收到客户发放的工资收入的劳动者，下文简称劳动者。
  
   管理员：平台共有三种角色——平台管理员（灵工平台实际运营方）、代理商管理员（代
  理推广方）、客户管理员（发放劳动报酬方）

# 平台方参考流程

1. 创建分包商。因为分包商需要申请一系列的第三方平台进行对接，因此不支持管理员后台添加，需要由开发者直接在数据库中创建，并同时添加对应的第三方平台参数。

3. 添加代理商(可选)。添加代理商时，分别设置此代理商在不同分包商下，平台收取的服务费比例 a。通过此代理商邀请的客户，无论收取客户多少比例的佣金 b，平台的收入均为比例 a，代理商的利润为比例 b-比例 a。

4. 添加客户。通过平台管理员添加的客户，不关联代理。向用户收取的所有服务费，全部视为平台的收入。客户分为三种客户：普通客户、免签客户、API 直连客户。

(1) 普通客户添加劳动者时，需要向劳动者发送确认签约短信。劳动者通过短信内的连接登录 H5 页面，进行在线签署合同，签署成功后方可发放薪资。

(2) 免签客户添加劳动者时，无需发送确认短信，系统会根据客户提供的劳动者身份证和姓名，静默生成签约合同。

(3) API 直连客户，无需在后台进行操作，可通过系统开放的第三方接口实现自动化业务处理。API 直连客户添加的劳动者，平台不与之创建合同，直接发放薪资。（API直连客户较为特殊，后台不直接显示创建入口，需要通过开发者在数据库中直接设置，并生成对应的 token）

5. 观察平台收益以及解决客户充值、提现、发票等业务。 代理方参考流程

1. 添加客户。通过代理商管理员添加的客户，自动关联代理。向用户收取的所有服务费，扣除代理与平台签订的服务费比例后，剩下的服务费比例差额为代理商利润。

2. 观察收益以及余额提现。 客户参考流程
  1. 添加灵活用工人员。支持手动导入以及 Excel 导入，正式导入之前有草稿箱功能，方便客户进行预审核。
     
  3. 创建劳动岗位。工资发放以及开票均需要对应的岗位，不同的岗位对应了不同的开票类目。
     
5. 将劳动者与劳动岗位进行关联。支持手动添加以及身份证号批量添加。
   
7. 创建工资单。工资单明细（劳动者以及发放金额）支持手动添加、Excel 导入、从岗位一键导入，导入后可手动调整。

8. 平台充值（可选）。客户需要先将发放的工资+预估服务费，充值到平台。只有当余额不低于实际扣除金额时，才可成功发放。充值方式有两种：

(1) 公对公银行转账无人值守充值。客户通过平台内预留的对公账户，向税地公司指定的对公账户进行转账，平台收到银行的转账记录后，会自动向客户余额中充值对应额度。

(2) 线下通过各种方式向平台运营方转账，然后平台管理员在后台给此用户手动充值对应的余额。

9. 发放工资。

10. 开具发票。 劳动者参考流程

1. 收到签约短信后，点击短信内的连接，进入登录页面。

2. 按照提示输入账号密码，登录成功后，查看待签约和已签约的合同。

3. 待签约的企业，点击去签约按钮，跳转 e 签宝平台进行签约，其中会进行要素认证。

4. 签约完成后，可查看工资发放记录

# 源码合作

![wx](https://github.com/user-attachments/assets/53259e87-4c72-45e6-93db-a76d97bf36e7)



# 界面展示

# 平台运营端

![001](https://github.com/user-attachments/assets/77a44528-dbab-4bcb-9794-791072430944)
![002](https://github.com/user-attachments/assets/76c5fbba-d5c4-4da2-9f02-ada51cb6025b)
![003](https://github.com/user-attachments/assets/edbb60b9-9af7-44b2-9718-cdfe99ea096f)
![004](https://github.com/user-attachments/assets/5a28873d-ca0e-4ff3-92e5-22780743f052)
![005](https://github.com/user-attachments/assets/df40db4b-3cae-44d1-8b4e-ba7cc22b5f34)
![007](https://github.com/user-attachments/assets/a71f04a7-a64e-40ad-a6d7-ae0ef1393a6c)
![009](https://github.com/user-attachments/assets/00d6654b-41f0-40be-8ba4-f025babca879)
![013](https://github.com/user-attachments/assets/38b8b50f-2665-41cd-9ae9-8f7de715ef1e)
![016](https://github.com/user-attachments/assets/2e4d86d8-4bf4-4181-b897-8c04d80a80b8)
![017](https://github.com/user-attachments/assets/a6dd621b-12ab-4e45-95c0-7bc4863b1c49)
![019](https://github.com/user-attachments/assets/999182ac-726e-4fdc-af6d-4476fdf0a1c0)


# 企业端

![01](https://github.com/user-attachments/assets/9ce9c4bf-d6da-4227-b098-31a1387b2f63)
![02](https://github.com/user-attachments/assets/402d71fa-ed23-4f91-8161-52577a96ed43)
![03](https://github.com/user-attachments/assets/59267bab-92eb-4241-b3d0-e83a496aa7b1)
![04](https://github.com/user-attachments/assets/42c10ebd-0b5e-4da0-8dd1-0501a877830b)
![05](https://github.com/user-attachments/assets/7acb14d8-b0f6-4818-9272-152ec4d7c8c2)
![06](https://github.com/user-attachments/assets/19d379e4-33c1-49ba-a839-118eeb66db7a)

![07](https://github.com/user-attachments/assets/7cc29354-fb09-4db3-ab69-ea6fc48d0100)



# 用户端（劳动者端）

![0001](https://github.com/user-attachments/assets/baf60970-fa25-4e6c-888a-ea403ae7aa9e)
![0002](https://github.com/user-attachments/assets/2b421ac0-070a-4aa2-a1ba-e2317e252d34)
![0003](https://github.com/user-attachments/assets/944f3535-7cf6-472d-8e59-6c08d5be44b2)
![0004](https://github.com/user-attachments/assets/e6055580-02de-4abf-87ce-4db1e26e8ac8)
![0005](https://github.com/user-attachments/assets/9dfa4469-9c36-4c79-97e6-6b66001bacf0)
![0006](https://github.com/user-attachments/assets/d4d582cc-6ef3-4d7d-bb89-a1f4f4dc47df)
![0007](https://github.com/user-attachments/assets/6feb85dc-5db9-448f-9526-e50c90423bff)












