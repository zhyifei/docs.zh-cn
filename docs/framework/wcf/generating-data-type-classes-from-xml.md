---
title: 从 XML 生成数据类型类
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: c1b5dfda8aa5370dbc202ab90c75ab5677970467
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59309337"
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="df2a8-102">从 XML 生成数据类型类</span><span class="sxs-lookup"><span data-stu-id="df2a8-102">Generating Data Type Classes from XML</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] <span data-ttu-id="df2a8-103">包括用于从 XML 生成数据类型类的新功能。</span><span class="sxs-lookup"><span data-stu-id="df2a8-103">includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="df2a8-104">本主题介绍如何为.NET 博客 RSS 源自动生成的数据类型。</span><span class="sxs-lookup"><span data-stu-id="df2a8-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="df2a8-105">获取从.NET 博客 RSS XML 源</span><span class="sxs-lookup"><span data-stu-id="df2a8-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1. <span data-ttu-id="df2a8-106">在 Internet Explorer 中，导航到[.NET 博客 RSS 源](https://devblogs.microsoft.com/dotnet/feed/)。</span><span class="sxs-lookup"><span data-stu-id="df2a8-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://devblogs.microsoft.com/dotnet/feed/).</span></span>  
  
2. <span data-ttu-id="df2a8-107">右键单击页并选择**查看源**。</span><span class="sxs-lookup"><span data-stu-id="df2a8-107">Right-click the page and select **View Source**.</span></span>  
  
3. <span data-ttu-id="df2a8-108">通过按复制的源文本**Ctrl + A**以选择所有文本，并**Ctrl + C**复制。</span><span class="sxs-lookup"><span data-stu-id="df2a8-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="df2a8-109">创建数据类型</span><span class="sxs-lookup"><span data-stu-id="df2a8-109">Creating the data types</span></span>  
  
1. <span data-ttu-id="df2a8-110">打开要使用代理的代码文件。</span><span class="sxs-lookup"><span data-stu-id="df2a8-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="df2a8-111">此文件应为 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 项目的一部分。</span><span class="sxs-lookup"><span data-stu-id="df2a8-111">This file should be part of a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] project.</span></span>  
  
2. <span data-ttu-id="df2a8-112">将游标放置于该文件中任何现有类之外的位置中。</span><span class="sxs-lookup"><span data-stu-id="df2a8-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3. <span data-ttu-id="df2a8-113">选择**编辑**，**选择性粘贴**，**将 XML 粘贴为类**。</span><span class="sxs-lookup"><span data-stu-id="df2a8-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4. <span data-ttu-id="df2a8-114">类名为`link`， `rss`， `rssChannel`， `rssChannelImage`，`rssChannelItem`和`rssChannelItemGuid`用于访问 RSS 源中的元素创建使用所需成员。</span><span class="sxs-lookup"><span data-stu-id="df2a8-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="df2a8-115">使用生成的类</span><span class="sxs-lookup"><span data-stu-id="df2a8-115">Using the generated classes</span></span>  
  
1. <span data-ttu-id="df2a8-116">一旦生成了类，这些类就可以像任何其他类一样在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="df2a8-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="df2a8-117">下面的代码示例返回 `rssChannelImage` 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="df2a8-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```
