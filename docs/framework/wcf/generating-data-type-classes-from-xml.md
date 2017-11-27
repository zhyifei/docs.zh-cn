---
title: "从 XML 生成数据类型类"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e0362673ebb7d686822fae594b3a41435ceb9a4d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="7ef60-102">从 XML 生成数据类型类</span><span class="sxs-lookup"><span data-stu-id="7ef60-102">Generating Data Type Classes from XML</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<span data-ttu-id="7ef60-103"> 包括用于从 XML 生成数据类型类的新功能。</span><span class="sxs-lookup"><span data-stu-id="7ef60-103"> includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="7ef60-104">本主题介绍如何为.NET 博客 RSS 源自动生成数据类型。</span><span class="sxs-lookup"><span data-stu-id="7ef60-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="7ef60-105">从.NET 博客 RSS 获取 XML 源</span><span class="sxs-lookup"><span data-stu-id="7ef60-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1.  <span data-ttu-id="7ef60-106">在 Internet Explorer 中，导航到[.NET 博客 RSS 源](https://blogs.msdn.microsoft.com/dotnet/feed/)。</span><span class="sxs-lookup"><span data-stu-id="7ef60-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://blogs.msdn.microsoft.com/dotnet/feed/).</span></span>  
  
2.  <span data-ttu-id="7ef60-107">右击该页并选择**查看源**。</span><span class="sxs-lookup"><span data-stu-id="7ef60-107">Right-click the page and select **View Source**.</span></span>  
  
3.  <span data-ttu-id="7ef60-108">通过按复制源的文本**Ctrl + A**若要选择所有文本和**Ctrl + C**复制。</span><span class="sxs-lookup"><span data-stu-id="7ef60-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="7ef60-109">创建数据类型</span><span class="sxs-lookup"><span data-stu-id="7ef60-109">Creating the data types</span></span>  
  
1.  <span data-ttu-id="7ef60-110">打开要使用代理的代码文件。</span><span class="sxs-lookup"><span data-stu-id="7ef60-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="7ef60-111">此文件应为 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 项目的一部分。</span><span class="sxs-lookup"><span data-stu-id="7ef60-111">This file should be part of a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="7ef60-112">将游标放置于该文件中任何现有类之外的位置中。</span><span class="sxs-lookup"><span data-stu-id="7ef60-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3.  <span data-ttu-id="7ef60-113">选择**编辑**，**选择性粘贴**，**将 XML 作为类粘贴**。</span><span class="sxs-lookup"><span data-stu-id="7ef60-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4.  <span data-ttu-id="7ef60-114">类调用`link`， `rss`， `rssChannel`， `rssChannelImage`，`rssChannelItem`和`rssChannelItemGuid`使用所需成员创建用于访问 RSS 源中的元素。</span><span class="sxs-lookup"><span data-stu-id="7ef60-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="7ef60-115">使用生成的类</span><span class="sxs-lookup"><span data-stu-id="7ef60-115">Using the generated classes</span></span>  
  
1.  <span data-ttu-id="7ef60-116">一旦生成了类，这些类就可以像任何其他类一样在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="7ef60-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="7ef60-117">下面的代码示例返回 `rssChannelImage` 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="7ef60-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```
