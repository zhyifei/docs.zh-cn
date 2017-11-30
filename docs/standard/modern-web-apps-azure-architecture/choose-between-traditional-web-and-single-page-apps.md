---
title: "传统 web 应用程序和单页面应用程序之间进行选择"
description: "使用 ASP.NET 核心和 Microsoft Azure 的架构师现代 web 应用程序"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 5bae77fc4e0df9d0bc7fecfad25adfcee2419084
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2017
---
# <a name="choose-between-traditional-web-apps-and-single-page-apps-spas"></a>传统 Web 应用程序和单页面应用程序 (Spa) 之间进行选择

> "Atwood 的法律： 任何应用程序可以编写在 JavaScript 中，将最终用 JavaScript 编写。"  
> _\-Jeff Atwood_

## <a name="summary"></a>摘要

到目前构建 web 应用程序的两种常规方法： 单页面应用程序 (Spa) 在 web 浏览器中执行大部分的用户界面逻辑服务器执行大多数应用程序逻辑的传统 web 应用程序与主要使用 web Api 的 web 服务器进行通信。 也可以混合方法，最简单正在承载一个或多个丰富类似 SPA 的子应用程序中的较大的传统 web 应用。

你应使用传统 web 应用程序时：

-   应用程序的客户端要求为简单或甚至是只读的。

-   你的应用程序需要在不支持 JavaScript 的浏览器中正常工作。

-   你的团队已熟悉 JavaScript 或 TypeScript 开发技术。

应使用 SPA 时：

-   你的应用程序必须公开具有许多功能的丰富的用户接口。

-   熟悉 JavaScript 和/或 TypeScript 开发你的团队。

-   你的应用程序必须已公开其他 （内部或公共） 的客户端的 api 的 API。

此外，SPA 框架要求更大体系结构和安全专业知识。 遇到比传统 web 应用程序由于频繁更新和新框架的更大改动。 配置自动化的生成和部署进程和利用窗格中列出的部署选项是与 SPA 应用程序比传统 web 应用程序更加困难。

在通过 SPA 模型的用户体验的改进必须权衡这些注意事项。

## <a name="when-to-choose-traditional-web-apps"></a>何时选择传统 web 应用程序

下面是选取传统 web 应用程序的以前所述原因的更多详细的说明。

**你的应用程序具有简单，可能是只读的、 客户端要求**

在以只读方式中，许多 web 应用程序主要由其用户绝大多数消耗。 只读 （或读取主要） 应用程序往往比那些维护和操作状态的大量简单得多。 例如，搜索引擎可能包括单一入口点与文本框中显示搜索结果的第二个页。 匿名用户可以轻松地请求，并且没有很少需要客户端逻辑。 同样，博客或内容管理系统的面向公众的应用程序通常包含主要的使用很少的客户端行为的内容。 此类应用程序轻松构建为 web 服务器上执行逻辑和呈现 HTML 浏览器中显示的传统的基于服务器的 web 应用程序中。 该站点的每个唯一页拥有自己的 URL 可标有书签并按搜索引擎索引 （默认情况下，而无需添加此作为独立的功能的应用程序） 也是此类情况下的一个明显好处。

**你的应用程序需要在不支持 JavaScript 的浏览器中正常工作**

需要能够在有限或者没有支持 JavaScript 的浏览器的 web 应用程序应使用传统 web 应用程序工作流编写的 （或至少能够故障回复到这种行为）。 Spa 才能正常; 需要客户端 JavaScript如果不可用，Spa 不是一个不错的选择。

**你的团队已熟悉 JavaScript 或 TypeScript 开发技术**

如果你的团队是熟悉 JavaScript 或 TypeScript，但熟悉服务器端 web 应用程序开发，则它们可能将能够比 SPA 更快速地交付的传统 web 应用。 除非学习到程序 Spa 是一个目标，或提供 SPA 的用户体验是必需的传统 web 应用程序均已熟悉生成它们的团队的提高工作效率选择。

## <a name="when-to-choose-spas"></a>何时选择 Spa

下面是开发的更多详细的说明何时选择单页面应用程序样式的 web 应用。

**你的应用程序必须公开具有许多功能的丰富的用户接口**

Spa 可以支持不需要重新加载该页面，因为用户执行的操作或应用程序的区域之间导航的丰富客户端功能。 Spa 可以加载更快地，提取在后台的数据和单个用户操作是更快地响应，因为完整的页面重新加载需要很少出现。 Spa 可以支持增量更新，用户无需单击一个按钮以提交表格保存部分完成窗体或文档。 Spa 可以比传统的应用程序更轻松地支持丰富的客户端行为，如拖动和删除。 Spa 可以用于对重新建立连接后最终同步回发到服务器的客户端模型进行更新以断开连接模式运行。 如果您的应用程序的要求包括超出典型 HTML 窗体提供的丰富功能，则应选择 SPA 样式的应用程序。

请注意，经常需要实现功能内置于传统 web 应用程序，如在地址栏反映当前的操作 （并允许到书签的用户或深层链接到此 URL，以返回到它） 中显示有意义的 URL 的 Spa。 Spa 还应允许用户用于浏览器的后退和前进按钮不会意外它们的结果。

**你的团队已熟悉 JavaScript 和/或 TypeScript 开发**

编写 Spa 需要熟悉 JavaScript 和/或 TypeScript 和客户端编程技术和库。 团队应在编写现代 JavaScript 使用角这样的 SPA 框架功能完善。

> ### <a name="references--spa-frameworks"></a>引用 – SPA 框架
> - **AngularJS**  
> <https://angularjs.org/>
> - **4 常用的 JavaScript 框架的比较**  
> <https://www.developereconomics.com/feature-comparison-of-4-popular-js-mv-frameworks>

**你的应用程序必须其他 （内部或公共） 的客户端公开了一个 API**

如果已正在以供其他客户端支持的 web API，则可能需要较少的工作量创建利用这些 Api，而不是无需复制在服务器端窗体中的逻辑的 SPA 实现。 用户与应用程序进行交互，Spa 对查询和更新数据进行广泛使用的 web Api。

## <a name="decision-table--traditional-web-or-spa"></a>决策表 – 传统 Web 或 SPA

以下的决策表总结了一些传统 web 应用程序和 SPA 之间进行选择时要考虑的基本因素。

  | **因素** | **传统 Web 应用** | **单页面应用程序** |
  |---|---|---|
  | 所需的团队熟悉 JavaScript/TypeScript | **最小** | **必需** |
  | 不带脚本的支持浏览器 | **支持** | **不支持** |
  | 最小的客户端应用程序行为 | **适合** | **太过严厉** |
  | 丰富而复杂的用户界面要求 | **限制** | **适合** |

>[!div class="step-by-step"]
[以前](现代-web 的应用程序-characteristics.md)[下一步](architectural-principles.md)
