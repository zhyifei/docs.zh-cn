---
title: "联合扩展性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d941175-74a2-4b15-81b3-086e8a95d25f
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 87121270d45637834b9499228075f49710073d21
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="syndication-extensibility"></a><span data-ttu-id="c0bdc-102">联合扩展性</span><span class="sxs-lookup"><span data-stu-id="c0bdc-102">Syndication Extensibility</span></span>
<span data-ttu-id="c0bdc-103">联合 API 是专为提供不限制格式的编程模型而设计的，该编程模型允许将联合内容以各种格式写入到网络中。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-103">The Syndication API is designed to provide a format-neutral programming model that allows syndicated content to be written to the wire in a variety of formats.</span></span> <span data-ttu-id="c0bdc-104">抽象数据模型由以下类组成：</span><span class="sxs-lookup"><span data-stu-id="c0bdc-104">The abstract data model consists of the following classes:</span></span>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
 <span data-ttu-id="c0bdc-105">这些类严格地映射到 Atom 1.0 规范中定义的构造，但有一些名称会不相同。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-105">These classes map closely to the constructs defined in the Atom 1.0 specification, although some of the names are different.</span></span>  
  
 <span data-ttu-id="c0bdc-106">联合协议的一个主要功能是扩展性。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-106">A key feature of syndication protocols is extensibility.</span></span> <span data-ttu-id="c0bdc-107">Atom 1.0 和 RSS 2.0 均向规范中未定义的联合源中添加属性和元素。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-107">Both Atom 1.0 and RSS 2.0, add attributes and elements to syndication feeds that are not defined in the specifications.</span></span> <span data-ttu-id="c0bdc-108">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 联合编程模型提供了以下使用自定义属性和扩展、松散类型访问以及派生新类的方式。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-108">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] syndication programming model provides the following ways of working with custom attributes and extensions, loosely-typed access and deriving a new class.</span></span>  
  
## <a name="loosely-typed-access"></a><span data-ttu-id="c0bdc-109">松散类型访问</span><span class="sxs-lookup"><span data-stu-id="c0bdc-109">Loosely Typed Access</span></span>  
 <span data-ttu-id="c0bdc-110">通过派生新类添加扩展的方式需要编写附加代码。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-110">Adding extensions by deriving a new class requires writing additional code.</span></span> <span data-ttu-id="c0bdc-111">另一种选择是以松散类型方式访问扩展。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-111">Another option is accessing extensions in a loosely-typed way.</span></span> <span data-ttu-id="c0bdc-112">联合抽象数据模型中定义的所有类型都包含名为 `AttributeExtensions` 和 `ElementExtensions` 的属性（但有一个例外，<xref:System.ServiceModel.Syndication.SyndicationContent> 具有 `AttributeExtensions` 属性，而不具有 `ElementExtensions` 属性）。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-112">All of the types defined in the syndication abstract data model contain properties named `AttributeExtensions` and `ElementExtensions` (with one exception, <xref:System.ServiceModel.Syndication.SyndicationContent> has an `AttributeExtensions` property but no `ElementExtensions` property).</span></span> <span data-ttu-id="c0bdc-113">这些属性是未经 `TryParseAttribute` 和 `TryParseElement` 方法分别处理的扩展的集合。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-113">These properties are collections of extensions not processed by the `TryParseAttribute` and `TryParseElement` methods respectively.</span></span> <span data-ttu-id="c0bdc-114">通过对 <xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection.ReadElementExtensions%2A?displayProperty=nameWithType>、`ElementExtensions`、<xref:System.ServiceModel.Syndication.SyndicationFeed>、<xref:System.ServiceModel.Syndication.SyndicationItem> 和 <xref:System.ServiceModel.Syndication.SyndicationLink> 的 <xref:System.ServiceModel.Syndication.SyndicationPerson> 属性调用 <xref:System.ServiceModel.Syndication.SyndicationCategory>，可以访问这些未处理的扩展。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-114">You can access these unprocessed extensions by calling <xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection.ReadElementExtensions%2A?displayProperty=nameWithType> on the `ElementExtensions` property of <xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem>, <xref:System.ServiceModel.Syndication.SyndicationLink>, <xref:System.ServiceModel.Syndication.SyndicationPerson>, and <xref:System.ServiceModel.Syndication.SyndicationCategory>.</span></span> <span data-ttu-id="c0bdc-115">这组方法将使用指定的名称和命名空间查找所有扩展，将其分别反序列化到 `TExtension` 的实例中，并将其作为 `TExtension` 对象的集合返回。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-115">This set of methods finds all extensions with the specified name and namespace, deserializes them individually into instances of `TExtension` and returns them as a collection of `TExtension` objects.</span></span>  
  
## <a name="deriving-a-new-class"></a><span data-ttu-id="c0bdc-116">派生新类</span><span class="sxs-lookup"><span data-stu-id="c0bdc-116">Deriving a New Class</span></span>  
 <span data-ttu-id="c0bdc-117">可以从任何现有抽象数据模型类派生新类。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-117">You can derive a new class from any of the existing abstract data model classes.</span></span> <span data-ttu-id="c0bdc-118">当实现一个应用程序并且您在其中使用的大多数源具有特殊扩展时，执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-118">Do this when implementing an application in which most of the feeds you are working with have a particular extension.</span></span> <span data-ttu-id="c0bdc-119">在本主题中，程序使用的大多数源都包含一个 `MyExtension` 扩展。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-119">In this topic, most of the feeds that the program works with contain a `MyExtension` extension.</span></span> <span data-ttu-id="c0bdc-120">若要提供改善的编程体验，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c0bdc-120">To provide an improved programming experience, do the following steps:</span></span>  
  
-   <span data-ttu-id="c0bdc-121">创建一个类以保留扩展数据。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-121">Create a class to hold the extension data.</span></span> <span data-ttu-id="c0bdc-122">在此例中，创建一个名为 MyExtension 的类。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-122">In this case, create a class called MyExtension.</span></span>  
  
-   <span data-ttu-id="c0bdc-123">从 <xref:System.ServiceModel.Syndication.SyndicationItem> 派生一个名为 MyExtensionItem 的类，公开一个 MyExtension 类型的属性以便编程。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-123">Derive a class called MyExtensionItem from <xref:System.ServiceModel.Syndication.SyndicationItem> to expose a property of type MyExtension for programmability purposes.</span></span>  
  
-   <span data-ttu-id="c0bdc-124">重写 MyExtensionItem 类中的 <xref:System.ServiceModel.Syndication.SyndicationItem.TryParseElement%28System.Xml.XmlReader%2CSystem.String%29>，以便在读入 MyExtension 时实例化新的 MyExtension 实例。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-124">Override <xref:System.ServiceModel.Syndication.SyndicationItem.TryParseElement%28System.Xml.XmlReader%2CSystem.String%29> in the MyExtensionItem class to instantiate a new MyExtension instance when a MyExtension is read in.</span></span>  
  
-   <span data-ttu-id="c0bdc-125">重写 MyExtensionItem 类中的 <xref:System.ServiceModel.Syndication.SyndicationItem.WriteElementExtensions%28System.Xml.XmlWriter%2CSystem.String%29>，以便将 MyExtension 属性的内容写入到 XML 编写器。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-125">Override <xref:System.ServiceModel.Syndication.SyndicationItem.WriteElementExtensions%28System.Xml.XmlWriter%2CSystem.String%29> in the MyExtensionItem class to write the contents of the MyExtension property to an XML writer.</span></span>  
  
-   <span data-ttu-id="c0bdc-126">从 <xref:System.ServiceModel.Syndication.SyndicationFeed> 派生一个名为 MyExtensionFeed 的类。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-126">Derive a class called MyExtensionFeed from <xref:System.ServiceModel.Syndication.SyndicationFeed>.</span></span>  
  
-   <span data-ttu-id="c0bdc-127">重写 MyExtensionFeed 类中的 <xref:System.ServiceModel.Syndication.SyndicationFeed.CreateItem>，以便实例化 MyExtensionItem 而非默认的 <xref:System.ServiceModel.Syndication.SyndicationItem>。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-127">Override <xref:System.ServiceModel.Syndication.SyndicationFeed.CreateItem> in the MyExtensionFeed class to instantiate a MyExtensionItem instead of the default <xref:System.ServiceModel.Syndication.SyndicationItem>.</span></span> <span data-ttu-id="c0bdc-128">在可以创建 <xref:System.ServiceModel.Syndication.SyndicationFeed>、<xref:System.ServiceModel.Syndication.SyndicationItem> 和 <xref:System.ServiceModel.Syndication.SyndicationLink> 对象（例如，<xref:System.ServiceModel.Syndication.SyndicationCategory>、<xref:System.ServiceModel.Syndication.SyndicationPerson> 和 <xref:System.ServiceModel.Syndication.SyndicationFeed.CreateLink>）的 <xref:System.ServiceModel.Syndication.SyndicationFeed.CreateCategory> 和 <xref:System.ServiceModel.Syndication.SyndicationFeed.CreatePerson> 中定义了一系列方法。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-128">A series of methods are defined in <xref:System.ServiceModel.Syndication.SyndicationFeed> and <xref:System.ServiceModel.Syndication.SyndicationItem> that can create <xref:System.ServiceModel.Syndication.SyndicationLink>, <xref:System.ServiceModel.Syndication.SyndicationCategory>, and <xref:System.ServiceModel.Syndication.SyndicationPerson> objects (for example, <xref:System.ServiceModel.Syndication.SyndicationFeed.CreateLink>, <xref:System.ServiceModel.Syndication.SyndicationFeed.CreateCategory>, and <xref:System.ServiceModel.Syndication.SyndicationFeed.CreatePerson>).</span></span> <span data-ttu-id="c0bdc-129">所有这些方法都可以重写以创建自定义派生类。</span><span class="sxs-lookup"><span data-stu-id="c0bdc-129">All of which can be overridden to create a custom derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0bdc-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0bdc-130">See Also</span></span>  
 [<span data-ttu-id="c0bdc-131">WCF 联合概述</span><span class="sxs-lookup"><span data-stu-id="c0bdc-131">WCF Syndication Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md)  
 [<span data-ttu-id="c0bdc-132">联合体系结构</span><span class="sxs-lookup"><span data-stu-id="c0bdc-132">Architecture of Syndication</span></span>](../../../../docs/framework/wcf/feature-details/architecture-of-syndication.md)
