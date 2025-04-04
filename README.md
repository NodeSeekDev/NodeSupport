# NodeSupport
NodeSupport计划是[NodeSeek社区](https://www.nodeseek.com/)和合作商家主导的免费服务器赞助计划，为高质量博客、开源项目、tg频道、App等持续提供优质稳定的服务器资源。

为了规范化、透明化赞助和审批流程，我们开发了[审批管理系统](https://support.nodeseek.com/)，用于处理免费机器的申请、续期、答疑、建议和检举投诉。

目前NodeSupport的vps服务器资源由[YxVM](https://yxvm.com/)大力赞助，项目处于试运营状态

# 总体设计
- 本Repo的[issue区](https://github.com/NodeSeekDev/NodeSupport/issues)用于公开和反馈审核流程
- 需要申请的用户在issue区提issue（类似工单），为统一格式，issue文本由[NodeSupport面板](https://support.nodeseek.com/)生成
- NS社区内dev和高级用户可以在论坛申请加入审核小组，来判断审核是否符合要求
- 通过论坛[开发的面板](https://support.nodeseek.com/)来管理、发放、记录兑换码，核验申请的网站和GitHub归属权

# 申请流程简介
- 用户在[NodeSupport面板](https://support.nodeseek.com/)通过NS账号登录面板，填写申请内容
- 根据NodeSupport面板生成的模板，到[GitHub项目](https://github.com/NodeSeekDev/NodeSupport/issues)发起申请issue
- 将生成的issue id填写到NodeSupport面板，提交申请记录
- 根据面板提醒，通过TXT记录、Github oAuth2、频道介绍文字等方法验证身份
- 申请赞助的用户，需要在网站/Github开源项目的readme/频道介绍等地方添加指定的赞助说明，参考下面详细说明
- 审批人员在Github issue区沟通和决定是否通过审批
- 如果通过申请，会在issue区留言反馈，用户可以自行到面板查看发放的兑换码
- 用户拿到兑换码后，可以自行到商家（[YxVM](https://yxvm.com/)）兑换机器

# 兑换码管理平台功能介绍
为了方便记录免费机器发放，自动验证申请者身份，社区开发一个简易的[兑换码管理平台](https://support.nodeseek.com/)
这样用户在GitHub发起申请时，会使用统一的模板化的描述，减少沟通成本，并且做到所有发放记录可查。
除此之外，平台还具备对域名归属、GitHub oAuth2、telegram 频道归属等自动验证身份的功能，减少核实所需要的等待时间

## 申请表单
申请内容的表单填写是整个流程的关键，也是决定了是否能够通过申请的因素之一
根据申请的依据（网站、GitHub项目、tg频道、桌面/手机app等），需要提供对应的申请信息
申请信息一般包括
- 申请依据的描述：如网站介绍、开源项目简要描述和
- 影响力证明，如访客量，可以来自于cloudflare统计、google统计、baidu统计、自建统计等，需截图
具体需要填写哪些内容可以直接在NodeSupport面板上看到

## 自动校验身份
目前[兑换码管理平台](https://support.nodeseek.com/)可以通过不同的方式来校验申请者身份，有助于节省申请审批中的沟通成本
- 网站，通过TXT记录校验
- GitHub项目，通过oAuth2校验
- 频道，通过描述文本校验
- app，尚无通用办法，人工沟通

# 审批门槛概览和一般化要求

是否通过审批，一般根据申请内容的质量和影响力决定
因为本项目尚处于初期草案/试运行阶段，因此这里给出一个粗略的参考标准，后期会逐渐细化和完善，并保持规则透明

## 审批门槛概览
|      | 配置A     | 配置B       | 配置C     | 配置D   |
|------|----------|----------|---------|---------|
| 网站   | 300 uv/月  | 500 uv/月   | 1k uv/月   | 2k uv/月   |
| 频道   | 1k 关注   | 3k 关注    | 6k 关注   | 10k关注   |
| 开源项目 | 200 star | 500 star | 2k star | 5k star |
| APP  | 500 下载   | 1k 下载    | 3k 下载   | 10k下载   |

目前的配置对应关系
- 配置A: YxVM | HKECO-Basic (1Cpu/767MB RAM)
- 配置B: YxVM | HKECO-Standard (1Cpu/1G RAM)
- 配置C: YxVM | HKECO-Advanced (2Cpu/2G RAM)
- 配置D: YxVM | HKECO-Luxury (4Cpu/4G RAM)
- 未启用/未定级配置： YxVM | SINECO-Basic (1Cpu/2G RAM)


## 一般化要求
- 如果自行撤除了赞助说明，视为放弃参与NodeSupport计划
- 如果通过后24小时内未添加赞助说明，会暂停或删除机器
- 申请得到的兑换码和机器不得转让和出售，并且使用时需要符合机器提供商的使用条款

# 网站类申请具体要求

- 网站需要尽量填写日访问量曲线和月访问量曲线截图
- 尽量提供基于js的统计结果（如Umami、宝塔、1panel、百度统计、谷歌统计），准确度比cf统计更高
- 域名成立时间需要在半年以上，免费二级域名网站根据质量限定门槛
- 要求在面板上验证通过后，先在申请资助的网站上添加说明，以降低审核成本
- 网站主要面向的是博客类型的内容站，其他类型根据影响力和质量综合评定，拒绝涉政和黄赌毒网站

## 申请通过后
- 需要在侧边栏或者其他地区放置一个简易的赞助说明[iframe组件](https://support.nodeget.com/page/promotion?id={your_id})
```
<!-- 代码参考，需要自行调整height和scale数值 -->
<iframe frameborder=0
src="https://support.nodeget.com/page/promotion?id={your_id}"
style="border-radius:8px; height: 246px;
transform: scale(1.0); transform-origin: top left;"></iframe>
```
- 如果博客长时间（如3个月）没有新的文章更新，商家有权停止赞助（参考标准草案，灵活执行）


# 频道类申请具体要求
频道目前专指telegram频道。频道需要提供月内用户增长曲线图，辅助判断是否有作弊嫌疑（刷量频道）

需要在频道描述或者置顶消息列表中提到NodeSupport项目，感谢YxVM。
示例：感谢NodeSupport和YxVM( @yxvmcom )对本频道的赞助和支持。

- 如果频道长时间（如3个月）没有新的内容更新，商家有权停止赞助（参考标准草案，灵活执行）

# 开源项目类申请具体要求
- 开源项目会根据项目质量和star用户质量判断是否有刷star嫌疑
- 主要在项目readme文件放置赞助说明组件的截图，并用md链接语法包裹，链接指向提供商
- 需要有NodeSupport赞助的中/英文说明（格式不限），用户可自行排版决定位置

参考：
```
[![image](iframe组件截图图片链接)](https://yxvm.com/)
[NodeSupport](https://github.com/NodeSeekDev/NodeSupport)赞助了本项目
```
- 对于开源项目的更新强度没有严格限制，尊重稳定的项目
- 对于Archive的或者公认为已废弃项目，商家有权停止赞助



# FAQ

1. **已经受资助的用户的用户，应该怎么处理**
在之前的活动里面已经申请过机器的用户，可以继续参与本项目申请
有社区处理审批相关，可以降低商家的工单成本，也有利于申请过程的透明化
审批通过后，如果剩余机器时长低于3个月可以同时持有之前的机器和当前审批的机器，如果超过3个月，用户需要在转移完数据后自行销毁老机器

2. **如果随着时间发展，可以申请更高配的机器怎么办**
在GitHub issue区发起升配issue，引用之前申请的机器

3. **已授权低配用户因审核标准改变而申请升级高配**
在GitHub issue区发起升配issue，引用之前申请的机器

4. **用户满足更高配条件却申请低配**
按照满足的最高配分配

# 对审核者，申请加入团队和审批规范
## 申请加入审核者团队
- 在[帖子](https://www.nodeseek.com/post-305185-1)内评论并@管理
- 最好是dev用户或者高等级用户，至少要对GitHub使用较为熟悉

## 审批结果规范
- accept：提出的申请信息符合规范，达到要求，已经在面板批复兑换码
- deny：对于要求符合程度低的，添加此标签，说明不符合原因，一段时间后关闭issue
- pending：对于不确定的需要继续讨论的，添加此标签，并且可以继续评论沟通
- downgrade：不满足申请表单的标准但满足低一些的申请标准的情况，按照实际符合的发放
- bellow_threshold：不符合最低要求的申请
- waiting_validation：未在面板上验证身份
- record_not_found：未在面板上查询到所在issue的id号

# 感谢
NodeSupport的兑换码管理平台由论坛内用户 [Croix](https://www.nodeseek.com/space/14356) 完整开发，是首次把社区内的开发计划交给论坛用户的尝试。

感谢[YxVM](https://yxvm.com/)对社区的信任，这个项目的诞生于和商家的沟通交流

感谢 [福尔摩斯](https://www.nodeseek.com/space/13352) 在整个项目内的沟通工作，感谢论坛内参与面板测试工作的[管理人员](https://www.nodeseek.com/post-192634-1)

# 其他
- NodeSeek对本计划保留最终解释权，对于一些预料之外的情况或者干扰项目运行的用户，会采取主观措施
- NodeSupport计划还处于草案与试运行阶段，有什么意见可以在此贴反馈
- 项目前期可能会做一些规范和流程上的调整，完善整个申请发放的逻辑
- 现在已经可以尝试申请，不过初期有可能出一些预料之外的问题，先跑通流程再说
