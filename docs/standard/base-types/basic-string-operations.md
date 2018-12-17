---
title: .NET 中的基本字符串操作
description: 了解可对字符串执行的基本操作。
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- strings [.NET Framework], basic string operations
- custom strings
ms.assetid: 8133d357-90b5-4b62-9927-43323d99b6b6
author: rpetrusha
ms.author: ronpet
ms.custom: seadec18
ms.openlocfilehash: 8621e79ad6e305f3859dc269965ecd216081f695
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53150675"
---
# <a name="basic-string-operations-in-net"></a><span data-ttu-id="c6647-103">.NET 中的基本字符串操作</span><span class="sxs-lookup"><span data-stu-id="c6647-103">Basic String Operations in .NET</span></span>
<span data-ttu-id="c6647-104">应用程序经常通过构造基于用户输入的消息来响应用户。</span><span class="sxs-lookup"><span data-stu-id="c6647-104">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="c6647-105">例如，网站用包含用户名的专用问候语来响应新登录的用户的情况并不少见。</span><span class="sxs-lookup"><span data-stu-id="c6647-105">For example, it is not uncommon for Web sites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span> <span data-ttu-id="c6647-106">使用 <xref:System.String?displayProperty=nameWithType> 和 <xref:System.Text.StringBuilder?displayProperty=nameWithType> 类中的多个方法，可以动态构造要在用户界面中显示的自定义字符串。</span><span class="sxs-lookup"><span data-stu-id="c6647-106">Several methods in the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="c6647-107">借助这些方法还可执行许多基本字符串操作，例如，从字节数组创建新字符串，比较字符串的值和修改现有字符串。</span><span class="sxs-lookup"><span data-stu-id="c6647-107">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c6647-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="c6647-108">In This Section</span></span>  
 [<span data-ttu-id="c6647-109">新建字符串</span><span class="sxs-lookup"><span data-stu-id="c6647-109">Creating New Strings</span></span>](../../../docs/standard/base-types/creating-new.md)  
 <span data-ttu-id="c6647-110">介绍了将对象转换为字符串以及合并字符串的基本方法。</span><span class="sxs-lookup"><span data-stu-id="c6647-110">Describes basic ways to convert objects into strings and to combine strings.</span></span>  
  
 [<span data-ttu-id="c6647-111">删减和删除字符</span><span class="sxs-lookup"><span data-stu-id="c6647-111">Trimming and Removing Characters</span></span>](../../../docs/standard/base-types/trimming.md)  
 <span data-ttu-id="c6647-112">介绍了如何修整或删除字符串中的字符。</span><span class="sxs-lookup"><span data-stu-id="c6647-112">Describes how to trim or remove characters in a string.</span></span>  
  
 [<span data-ttu-id="c6647-113">填充字符串</span><span class="sxs-lookup"><span data-stu-id="c6647-113">Padding Strings</span></span>](../../../docs/standard/base-types/padding.md)  
 <span data-ttu-id="c6647-114">介绍如何将字符或空格插入到字符串中。</span><span class="sxs-lookup"><span data-stu-id="c6647-114">Describes how to insert characters or empty spaces into a string.</span></span>  
  
 [<span data-ttu-id="c6647-115">比较字符串</span><span class="sxs-lookup"><span data-stu-id="c6647-115">Comparing Strings</span></span>](../../../docs/standard/base-types/comparing.md)  
 <span data-ttu-id="c6647-116">介绍了如何比较两个或多个字符串的内容。</span><span class="sxs-lookup"><span data-stu-id="c6647-116">Describes how to compare the contents of two or more strings.</span></span>  
  
 [<span data-ttu-id="c6647-117">更改大小写</span><span class="sxs-lookup"><span data-stu-id="c6647-117">Changing Case</span></span>](../../../docs/standard/base-types/changing-case.md)  
 <span data-ttu-id="c6647-118">介绍了如何更改字符串中的字符大小写。</span><span class="sxs-lookup"><span data-stu-id="c6647-118">Describes how to change the case of characters within a string.</span></span>  
  
 [<span data-ttu-id="c6647-119">使用 StringBuilder 类</span><span class="sxs-lookup"><span data-stu-id="c6647-119">Using the StringBuilder Class</span></span>](../../../docs/standard/base-types/stringbuilder.md)  
 <span data-ttu-id="c6647-120">介绍了如何使用 <xref:System.Text.StringBuilder> 类创建和修改动态字符串对象。</span><span class="sxs-lookup"><span data-stu-id="c6647-120">Describes how to create and modify dynamic string objects with the <xref:System.Text.StringBuilder> class.</span></span>  
  
 [<span data-ttu-id="c6647-121">如何：执行基本的字符串控制</span><span class="sxs-lookup"><span data-stu-id="c6647-121">How to: Perform Basic String Manipulations</span></span>](../../../docs/standard/base-types/basic-manipulations.md)  
 <span data-ttu-id="c6647-122">展示了如何使用基本字符串操作。</span><span class="sxs-lookup"><span data-stu-id="c6647-122">Demonstrates the use of basic string operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c6647-123">相关章节</span><span class="sxs-lookup"><span data-stu-id="c6647-123">Related Sections</span></span>  
 [<span data-ttu-id="c6647-124">.NET 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="c6647-124">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="c6647-125">介绍了如何从一种类型转换为另一种类型。</span><span class="sxs-lookup"><span data-stu-id="c6647-125">Describes how to convert one type into another type.</span></span>  
  
 [<span data-ttu-id="c6647-126">格式设置类型</span><span class="sxs-lookup"><span data-stu-id="c6647-126">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="c6647-127">介绍了如何使用格式说明符设置字符串格式。</span><span class="sxs-lookup"><span data-stu-id="c6647-127">Describes how to format strings using format specifiers.</span></span>
