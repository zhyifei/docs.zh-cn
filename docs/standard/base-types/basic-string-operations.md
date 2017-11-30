---
title: ".NET Framework 中的基本字符串操作"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strings [.NET Framework], basic string operations
- custom strings
ms.assetid: 8133d357-90b5-4b62-9927-43323d99b6b6
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f241b99f97cad081a65fd8654169e444a1b588cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="basic-string-operations-in-net"></a><span data-ttu-id="45dc2-102">.NET 中的基本字符串操作</span><span class="sxs-lookup"><span data-stu-id="45dc2-102">Basic String Operations in .NET</span></span>
<span data-ttu-id="45dc2-103">应用程序经常通过构造基于用户输入的消息来响应用户。</span><span class="sxs-lookup"><span data-stu-id="45dc2-103">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="45dc2-104">例如，网站用包含用户名的专用问候语来响应新登录的用户的情况并不少见。</span><span class="sxs-lookup"><span data-stu-id="45dc2-104">For example, it is not uncommon for Web sites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span> <span data-ttu-id="45dc2-105">中的一些方法<xref:System.String?displayProperty=nameWithType>和<xref:System.Text.StringBuilder?displayProperty=nameWithType>类，可以动态构造自定义要在你的用户界面中显示的字符串。</span><span class="sxs-lookup"><span data-stu-id="45dc2-105">Several methods in the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="45dc2-106">借助这些方法还可执行许多基本字符串操作，例如，从字节数组创建新字符串，比较字符串的值和修改现有字符串。</span><span class="sxs-lookup"><span data-stu-id="45dc2-106">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="45dc2-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="45dc2-107">In This Section</span></span>  
 [<span data-ttu-id="45dc2-108">新建字符串</span><span class="sxs-lookup"><span data-stu-id="45dc2-108">Creating New Strings</span></span>](../../../docs/standard/base-types/creating-new.md)  
 <span data-ttu-id="45dc2-109">描述基本的方式将对象转换为字符串并将字符串合并。</span><span class="sxs-lookup"><span data-stu-id="45dc2-109">Describes basic ways to convert objects into strings and to combine strings.</span></span>  
  
 [<span data-ttu-id="45dc2-110">删减和删除字符</span><span class="sxs-lookup"><span data-stu-id="45dc2-110">Trimming and Removing Characters</span></span>](../../../docs/standard/base-types/trimming.md)  
 <span data-ttu-id="45dc2-111">描述如何剪裁或字符串中移除字符。</span><span class="sxs-lookup"><span data-stu-id="45dc2-111">Describes how to trim or remove characters in a string.</span></span>  
  
 [<span data-ttu-id="45dc2-112">填充字符串</span><span class="sxs-lookup"><span data-stu-id="45dc2-112">Padding Strings</span></span>](../../../docs/standard/base-types/padding.md)  
 <span data-ttu-id="45dc2-113">介绍如何将字符或空格插入到字符串中。</span><span class="sxs-lookup"><span data-stu-id="45dc2-113">Describes how to insert characters or empty spaces into a string.</span></span>  
  
 [<span data-ttu-id="45dc2-114">比较字符串</span><span class="sxs-lookup"><span data-stu-id="45dc2-114">Comparing Strings</span></span>](../../../docs/standard/base-types/comparing.md)  
 <span data-ttu-id="45dc2-115">描述如何比较两个或多个字符串的内容。</span><span class="sxs-lookup"><span data-stu-id="45dc2-115">Describes how to compare the contents of two or more strings.</span></span>  
  
 [<span data-ttu-id="45dc2-116">更改大小写</span><span class="sxs-lookup"><span data-stu-id="45dc2-116">Changing Case</span></span>](../../../docs/standard/base-types/changing-case.md)  
 <span data-ttu-id="45dc2-117">介绍如何更改字符串中字符的大小写。</span><span class="sxs-lookup"><span data-stu-id="45dc2-117">Describes how to change the case of characters within a string.</span></span>  
  
 [<span data-ttu-id="45dc2-118">使用 StringBuilder 类</span><span class="sxs-lookup"><span data-stu-id="45dc2-118">Using the StringBuilder Class</span></span>](../../../docs/standard/base-types/stringbuilder.md)  
 <span data-ttu-id="45dc2-119">描述如何创建和修改与动态字符串对象<xref:System.Text.StringBuilder>类。</span><span class="sxs-lookup"><span data-stu-id="45dc2-119">Describes how to create and modify dynamic string objects with the <xref:System.Text.StringBuilder> class.</span></span>  
  
 [<span data-ttu-id="45dc2-120">如何：执行基本的字符串控制</span><span class="sxs-lookup"><span data-stu-id="45dc2-120">How to: Perform Basic String Manipulations</span></span>](../../../docs/standard/base-types/basic-manipulations.md)  
 <span data-ttu-id="45dc2-121">演示如何使用基本字符串操作。</span><span class="sxs-lookup"><span data-stu-id="45dc2-121">Demonstrates the use of basic string operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="45dc2-122">相关章节</span><span class="sxs-lookup"><span data-stu-id="45dc2-122">Related Sections</span></span>  
 [<span data-ttu-id="45dc2-123">.NET 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="45dc2-123">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="45dc2-124">描述如何将一个类型转换为另一种类型。</span><span class="sxs-lookup"><span data-stu-id="45dc2-124">Describes how to convert one type into another type.</span></span>  
  
 [<span data-ttu-id="45dc2-125">格式设置类型</span><span class="sxs-lookup"><span data-stu-id="45dc2-125">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="45dc2-126">描述如何格式字符串使用格式说明符。</span><span class="sxs-lookup"><span data-stu-id="45dc2-126">Describes how to format strings using format specifiers.</span></span>
