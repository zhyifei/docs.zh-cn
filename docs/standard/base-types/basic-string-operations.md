---
title: "基本字符串操作"
description: "基本字符串操作"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 9658098d-de60-4868-ba5b-0c278748a90f
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: b8bdbeccd226c412e725200fcaf81ec568afc5bc
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="basic-string-operations"></a><span data-ttu-id="79c8b-104">基本字符串操作</span><span class="sxs-lookup"><span data-stu-id="79c8b-104">Basic string operations</span></span>

<span data-ttu-id="79c8b-105">应用程序经常通过构造基于用户输入的消息来响应用户。</span><span class="sxs-lookup"><span data-stu-id="79c8b-105">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="79c8b-106">例如，网站用包含用户名的专用问候语来响应新登录的用户的情况并不少见。</span><span class="sxs-lookup"><span data-stu-id="79c8b-106">For example, it is not uncommon for Web sites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span> <span data-ttu-id="79c8b-107">使用 [System.String](xref:System.String) 和 [System.Text.StringBuilder](xref:System.Text.StringBuilder) 类中的多个方法可以动态构造要在用户界面中显示的自定义字符串。</span><span class="sxs-lookup"><span data-stu-id="79c8b-107">Several methods in the [System.String](xref:System.String) and [System.Text.StringBuilder](xref:System.Text.StringBuilder) classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="79c8b-108">借助这些方法还可执行许多基本字符串操作，例如，从字节数组创建新字符串，比较字符串的值和修改现有字符串。</span><span class="sxs-lookup"><span data-stu-id="79c8b-108">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="79c8b-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="79c8b-109">In This Section</span></span>

<span data-ttu-id="79c8b-110">[创建新字符串](creating-new.md) - 介绍将对象转换为字符串以及合并字符串的基本方法。</span><span class="sxs-lookup"><span data-stu-id="79c8b-110">[Creating new strings](creating-new.md) - Describes basic ways to convert objects into strings and to combine strings.</span></span>

<span data-ttu-id="79c8b-111">[剪裁和移除字符](trimming.md) - 介绍如何剪裁或移除字符串中的字符。</span><span class="sxs-lookup"><span data-stu-id="79c8b-111">[Trimming and removing characters](trimming.md) - Describes how to trim or remove characters in a string.</span></span> 

<span data-ttu-id="79c8b-112">[填充字符串](padding.md) - 介绍如何将字符或空格插入到字符串中。</span><span class="sxs-lookup"><span data-stu-id="79c8b-112">[Padding strings](padding.md) - Describes how to insert characters or empty spaces into a string.</span></span>

<span data-ttu-id="79c8b-113">[比较字符串](comparing.md) - 介绍如何比较两个或更多个字符串的内容。</span><span class="sxs-lookup"><span data-stu-id="79c8b-113">[Comparing strings](comparing.md) - Describes how to compare the contents of two or more strings.</span></span>

<span data-ttu-id="79c8b-114">[更改大小写](changing-case.md) - 介绍如何更改字符串中字符的大小写。</span><span class="sxs-lookup"><span data-stu-id="79c8b-114">[Changing case](changing-case.md) - Describes how to change the case of characters within a string.</span></span>

<span data-ttu-id="79c8b-115">[使用 StringBuilder 类](stringbuilder.md) - 介绍如何用 [StringBuilder](xref:System.Text.StringBuilder) 类创建和修改动态字符串对象。</span><span class="sxs-lookup"><span data-stu-id="79c8b-115">[Using the StringBuilder class](stringbuilder.md) - Describes how to create and modify dynamic string objects with the [StringBuilder](xref:System.Text.StringBuilder) class.</span></span>

<span data-ttu-id="79c8b-116">[如何：执行基本字符串操作](basic-manipulations.md) - 演示基本字符串操作的用法。</span><span class="sxs-lookup"><span data-stu-id="79c8b-116">[How to: Perform basic string manipulations](basic-manipulations.md) - Demonstrates the use of basic string operations.</span></span>

## <a name="related-sections"></a><span data-ttu-id="79c8b-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="79c8b-117">Related Sections</span></span>

<span data-ttu-id="79c8b-118">[类型转换](type-conversion.md) - 介绍如何从一种类型转换为另一种类型。</span><span class="sxs-lookup"><span data-stu-id="79c8b-118">[Type conversion](type-conversion.md) - Describes how to convert from one type to another.</span></span>

<span data-ttu-id="79c8b-119">[格式设置类型](formatting-types.md) - 介绍如何使用字符串格式说明符对字符串设置格式。</span><span class="sxs-lookup"><span data-stu-id="79c8b-119">[Formatting types](formatting-types.md) - Describes how to format strings using the string format specifiers.</span></span>



