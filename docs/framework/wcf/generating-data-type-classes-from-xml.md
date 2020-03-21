---
title: 从 XML 生成数据类型类
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: d66cbd1806b90d21a483d0c470f953ddfb9c4fca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184135"
---
# <a name="generating-data-type-classes-from-xml"></a>从 XML 生成数据类型类
.NET 框架 4.5 包括一个新功能，用于从 XML 生成数据类型类。 本主题介绍如何自动为 .NET 博客 RSS 源生成数据类型。  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a>从 .NET 博客 RSS 源获取 XML  
  
1. 在 Internet 资源管理器中，导航到[.NET 博客 RSS 源](https://devblogs.microsoft.com/dotnet/feed/)。  
  
2. 右键单击页面并选择 **"查看源**"。  
  
3. 通过按**Ctrl_A**以选择所有文本复制源的文本，然后**按 Ctrl_C**进行复制。  
  
### <a name="creating-the-data-types"></a>创建数据类型  
  
1. 打开要使用代理的代码文件。 此文件应是 .NET 框架 4.5 项目的一部分。  
  
2. 将游标放置于该文件中任何现有类之外的位置中。  
  
3. 选择 **"编辑**"、"**粘贴特殊**"、"**粘贴XML为类**"。  
  
4. 使用访问`link` `rss`RSS 源中的元素的必要成员`rssChannel`创建名为 、、`rssChannelImage``rssChannelItem`和`rssChannelItemGuid`的类。  
  
### <a name="using-the-generated-classes"></a>使用生成的类  
  
1. 一旦生成了类，这些类就可以像任何其他类一样在代码中使用。 下面的代码示例返回 `rssChannelImage` 类的新实例。  
  
    ```csharp
    var channelImage = new rssChannelImage()
    {
        title = "MyImage",
        link = "http://www.contoso.com/images/channelImage.jpg",
        url = "http://www.contoso.com/entries/myEntry.html"
    };  
    ```
