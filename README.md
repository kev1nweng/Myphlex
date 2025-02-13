# 秘符灵匣 Myphlex

一个将高安全性、高兼容性、高便利性以及众多新颖特征集成于一体的跨平台密码器解决方案。

这里是 `秘符灵匣 Myphlex` 的主仓库。该项目分为两个部分，分别作为 `submodule` 引入。

- `myph` - 密码器服务端；
- `lex` - 密码器客户端。

## 📖 配置说明书

仅第一次使用秘符灵匣时需进行配置。**部署完成后进入网页，设置面板会自动弹出。**

1. **设置动态秘符规则**

   > 例如，假设您设置的动态密码规则是 `d3-d2-d1-t3-t2-t1`，
   > 且现在是 2025 年 2 月 13 日 15 点 10 分 05 秒（即实时日期显示为 `25.02.13 15:10:05`），
   > 则您这个时刻的动态密码为：`052151`。

   ```
   y  y .m  m :d  d  h  h :m  m :s  s 
   d1 d2 d3 d4 d5 d6 t1 t2 t3 t4 t5 t6
   ```

   此动态秘符用于激活密码生成器，动态更安全。
   秘符规则决定了当前日期会被如何组合在一起构成您的动态密钥。

   > [!TIP]
   > 建议在您的规则中包含 "t4"，如此您的动态密钥将每分钟变动一次，安全性较高。
   > 相应地，不建议您在规则中包含 "t5" 或 "t6"，因为它们每 10 秒或 1 秒变动一次，
   > 后续可供您输入动态密码的时间太短。**您需要在密钥的有效期内输完密码。**


2. **按照面板上的提示设置其他密码特征**
   
   即您想要密码生成器生成的，用于各个平台的密码的统一特征：
   如前缀为kW、后缀为$、中间部分长度8。
   
   `密码种子 1`、`密码种子 2` 是用于产生真随机性的两个数字，
   您可以拖动滑条任意选择，仅用于增强安全性。

---

完成以上设置后进入**灵匣密码器**页面。

1. **在“动态密码”框内输入动态密码**

   > 例如：之前设置的秘符规则是 `d3-d2-d1-t3-t2-t1`，而当前时间（在输入框上方显示）
   > 是 `25.02.13 15:10:01`，您的动态密码则是 `052151`。

   > [!NOTE]
   > 虽然您的动态密码每分钟变动一次，但您生成的密码并不会改变。

2. **在 “密码 ID” 框内输入您想提取的平台的密码的 ID 名称**

   > 例如：AppleID、微信、163邮箱、工作邮箱、支付宝、...游戏平台、...银行网银等

   密码 ID 可以就是平台的名称（这样比较好记），也可以是其他任何自定义名称。
   
   > [!IMPORTANT]  
   > 不同平台密码的 ID 必须是 **两两不一致的**（否则会生成完全相同的密码）。

   > [!NOTE]  
   > 该密码 ID **不区分大小写**。例如，`AppleID` 和 `aPPleiD` 是等价的。

3. **动态密码认证通过后点“获取密码”**

   即生成某平台密码并复制到剪贴板。
   如之前设置密码特征为 “前缀为Lee、后缀为\$、中间部分长度8”，则生成的密码应该为 `Lee********$`。

4. **打开密码使用平台**

   找到您正在使用的平台的密码修改区域，把密码修改成秘符灵匣生成的密码。

---

从此，您无需记忆任何密码。每当您需要某平台密码时：
- 打开秘符灵匣；
- 在 “动态密码” 框内，根据您的规则输入动态密码；
- 在 “密码ID” 框内输入平台 ID 名称；
- 点击 “获取密码”，即可提取到该平台密码至剪贴板。此时可以粘贴密码；
- （可选）点击页面左上角的秘符状态指示按钮并注销会话；
   > [!NOTE]  
   > 即使您不手动注销会话，秘符灵匣也会自动在 10 分钟后注销您的会话。
- 至此一次密码调取完成。

> [!WARNING]  
> 为您的数据安全着想，建议您在使用完密码后立即清空剪贴板，尤其是当您在公共设备上使用秘符灵匣时。
