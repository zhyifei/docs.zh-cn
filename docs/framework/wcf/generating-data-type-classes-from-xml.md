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
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="5484c-102">从 XML 生成数据类型类</span><span class="sxs-lookup"><span data-stu-id="5484c-102">Generating Data Type Classes from XML</span></span>
<span data-ttu-id="5484c-103">.NET 框架 4.5 包括一个新功能，用于从 XML 生成数据类型类。</span><span class="sxs-lookup"><span data-stu-id="5484c-103">.NET Framework 4.5 includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="5484c-104">本主题介绍如何自动为 .NET 博客 RSS 源生成数据类型。</span><span class="sxs-lookup"><span data-stu-id="5484c-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="5484c-105">从 .NET 博客 RSS 源获取 XML</span><span class="sxs-lookup"><span data-stu-id="5484c-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1. <span data-ttu-id="5484c-106">在 Internet 资源管理器中，导航到[.NET 博客 RSS 源](https://devblogs.microsoft.com/dotnet/feed/)。</span><span class="sxs-lookup"><span data-stu-id="5484c-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://devblogs.microsoft.com/dotnet/feed/).</span></span>  
  
2. <span data-ttu-id="5484c-107">右键单击页面并选择 **"查看源**"。</span><span class="sxs-lookup"><span data-stu-id="5484c-107">Right-click the page and select **View Source**.</span></span>  
  
3. <span data-ttu-id="5484c-108">通过按**Ctrl_A**以选择所有文本复制源的文本，然后**按 Ctrl_C**进行复制。</span><span class="sxs-lookup"><span data-stu-id="5484c-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="5484c-109">创建数据类型</span><span class="sxs-lookup"><span data-stu-id="5484c-109">Creating the data types</span></span>  
  
1. <span data-ttu-id="5484c-110">打开要使用代理的代码文件。</span><span class="sxs-lookup"><span data-stu-id="5484c-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="5484c-111">此文件应是 .NET 框架 4.5 项目的一部分。</span><span class="sxs-lookup"><span data-stu-id="5484c-111">This file should be part of a .NET Framework 4.5 project.</span></span>  
  
2. <span data-ttu-id="5484c-112">将游标放置于该文件中任何现有类之外的位置中。</span><span class="sxs-lookup"><span data-stu-id="5484c-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3. <span data-ttu-id="5484c-113">选择 **"编辑**"、"**粘贴特殊**"、"**粘贴XML为类**"。</span><span class="sxs-lookup"><span data-stu-id="5484c-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4. <span data-ttu-id="5484c-114">使用访问`link` `rss`RSS 源中的元素的必要成员`rssChannel`创建名为 、、`rssChannelImage``rssChannelItem`和`rssChannelItemGuid`的类。</span><span class="sxs-lookup"><span data-stu-id="5484c-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="5484c-115">使用生成的类</span><span class="sxs-lookup"><span data-stu-id="5484c-115">Using the generated classes</span></span>  
  
1. <span data-ttu-id="5484c-116">一旦生成了类，这些类就可以像任何其他类一样在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="5484c-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="5484c-117">下面的代码示例返回 `rssChannelImage` 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="5484c-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```csharp
    var channelImage = new rssChannelImage()
    {
        title = "MyImage",
        link = "http://www.contoso.com/images/channelImage.jpg",
        url = "http://www.contoso.com/entries/myEntry.html"
    };  
    ```
