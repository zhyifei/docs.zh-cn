---
title: "类型提供程序疑难解答"
description: "发现问题的最有可能，若要在 F # 中使用类型提供程序时遇到的潜在的解决方案。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 44533045-9862-43c5-81d9-3e05157e975a
ms.openlocfilehash: 2b54454d7950dfdd6512d849fd739f505ef3317d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="troubleshooting-type-providers"></a>类型提供程序疑难解答

本主题介绍并提供最有可能，若要使用类型提供程序时遇到的问题的潜在解决方案。


## <a name="possible-problems-with-type-providers"></a>用类型提供程序可能存在的问题
如果你遇到问题，当您使用类型提供程序时，你可以查看下表中的最常见的解决方案。



|问题|建议的操作|
|-------|-----------------|
|**架构更改**。 类型提供程序的效果最佳的数据源架构时保持不变。 如果你添加的数据的表或列，或更改该架构的另一个，类型提供程序无法自动识别这些更改。|清理或重新生成项目。 若要清除该项目，选择**生成**，**清理** *ProjectName*菜单栏上。 若要重新生成项目，选择**生成**，**重新生成** *ProjectName*菜单栏上。 这些操作重置所有类型提供程序状态，并强制要重新连接到数据源并获取更新的架构信息的提供程序。|
|**连接失败**。 URL 或连接字符串不正确、 网络已关闭，或者数据源或服务不可用。|对于 web 服务或 OData 服务，你可以尝试在 Internet Explorer 中以验证是否 URL 正确无误且服务可用的 URL。 对于数据库连接字符串，你可以使用中的数据连接工具**服务器资源管理器**以验证是否是有效的连接字符串和数据库是否可用。 还原你的连接之后，你应然后清理或重新生成项目，以便类型提供程序将重新连接到网络。|
|**不是有效的凭据**。 您必须具有有效权限的数据源或 web 服务。|对于 SQL 连接，用户名和连接字符串或配置文件中指定的密码必须是有效的数据库。 如果使用 Windows 身份验证，你必须具有对数据库的访问。 数据库管理员可以标识所需的权限对每个数据库和数据库中的每个元素的访问。<br /><br />对于 web 服务或数据服务，你必须具有相应凭据。 大多数类型提供程序提供 DataContext 对象，它包含你可以使用相应的用户名和访问密钥设置的凭据属性。|
|**不是有效的路径**。 文件的路径无效。|验证是否路径正确无误，并且该文件存在。 此外，你必须相应地 quote 路径中的任何 backlashes 或使用原义字符串或三引号字符串。|

## <a name="see-also"></a>另请参阅
[类型提供程序](index.md)
