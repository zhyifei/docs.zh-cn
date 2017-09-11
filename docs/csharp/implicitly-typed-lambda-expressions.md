---
title: "隐式类型化 lambda 表达式"
description: "了解为什么不能使用隐式类型化变量声明来声明 lambda 表达式。"
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a3851da9-e018-4389-9922-233db7d0f841
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 663613af001f9727c48bd48553540305e47a6bab
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="implicitly-typed-lambda-expressions"></a><span data-ttu-id="1cc84-104">隐式类型化 lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="1cc84-104">Implicitly typed lambda expressions</span></span>

<span data-ttu-id="1cc84-105">我没有使用 `var` 声明此表达式树。</span><span class="sxs-lookup"><span data-stu-id="1cc84-105">I'm not using `var` to declare this expression tree.</span></span> <span data-ttu-id="1cc84-106">不能使用隐式类型化变量声明来声明 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="1cc84-106">You can't use an implicitly typed variable declaration to declare a lambda expression.</span></span>
<span data-ttu-id="1cc84-107">它会对编译器造成循环逻辑问题。</span><span class="sxs-lookup"><span data-stu-id="1cc84-107">It creates a circular logic problem for the compiler.</span></span> <span data-ttu-id="1cc84-108">`var` 声明会告知编译器通过赋值运算符右侧的表达式的类型查明变量的类型。</span><span class="sxs-lookup"><span data-stu-id="1cc84-108">The `var` declaration tells the compiler to figure out the type of the variable from the type of expression on the right hand side of the assignment operator.</span></span> <span data-ttu-id="1cc84-109">Lambda 表达式没有编译时类型，但是可转换为任何匹配委托或表达式类型。</span><span class="sxs-lookup"><span data-stu-id="1cc84-109">A lambda expression does not have a compile time type, but is convertible to any matching delegate or expression type.</span></span> <span data-ttu-id="1cc84-110">将 lambda 表达式分配给委托或表达式类型的变量时，可告知编译器尝试并将 lambda 表达式转换为与“分配对象”变量的签名匹配的表达式或委托。</span><span class="sxs-lookup"><span data-stu-id="1cc84-110">When you assign a lambda expression to a variable of a delegate or expression type, you tell the compiler to try and convert the lambda expression into an expression or delegate that matches the signature of the 'assigned to' variable.</span></span> <span data-ttu-id="1cc84-111">编译器必须尝试使赋值右侧的内容与赋值左侧的类型匹配。</span><span class="sxs-lookup"><span data-stu-id="1cc84-111">The compiler must try to make the thing on the right hand side of the assignment match the type on the left hand side of the assignment.</span></span> 

<span data-ttu-id="1cc84-112">赋值两侧都无法告知编译器查看赋值运算符另一侧的对象并查看我的类型是否匹配。</span><span class="sxs-lookup"><span data-stu-id="1cc84-112">Both sides of the assignment can't be telling the compiler to look at the object on the other side of the assignment operator and see if my type matches.</span></span>

<span data-ttu-id="1cc84-113">通过阅读[这篇文章](http://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/type-inference.pdf)（PDF 下载），甚至可以获得有关 C# 语言为何指定该行为的详细信息</span><span class="sxs-lookup"><span data-stu-id="1cc84-113">You can get even more details on why the C# language specifies that behavior by reading [this article](http://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/type-inference.pdf) (PDF Download)</span></span>



