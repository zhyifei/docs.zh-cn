---
title: "浮点数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73c218c6-1c44-4402-a167-4f6262629a91
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9a090d02b9c2ce63bd265996d237aab5c30f61bf
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="floating-point-numbers"></a><span data-ttu-id="4ab2f-102">浮点数</span><span class="sxs-lookup"><span data-stu-id="4ab2f-102">Floating-Point Numbers</span></span>
<span data-ttu-id="4ab2f-103">此主题描述了开发人员在 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 中使用浮点数时经常遇到的一些问题。</span><span class="sxs-lookup"><span data-stu-id="4ab2f-103">This topic describes some of the issues that developers frequently encounter when they work with floating-point numbers in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span></span> <span data-ttu-id="4ab2f-104">这些问题是由计算机存储浮点数的方式所导致的，并不是特定提供程序（如 <xref:System.Data.SqlClient> 或 <xref:System.Data.OracleClient>）所特有的。</span><span class="sxs-lookup"><span data-stu-id="4ab2f-104">These issues are caused by the way that computers store floating-point numbers, and are not specific to a particular provider such as <xref:System.Data.SqlClient> or <xref:System.Data.OracleClient>.</span></span>  
  
 <span data-ttu-id="4ab2f-105">浮点数一般没有准确的二进制表示形式，</span><span class="sxs-lookup"><span data-stu-id="4ab2f-105">Floating-point numbers generally do not have an exact binary representation.</span></span> <span data-ttu-id="4ab2f-106">计算机只是存储数字的近似值。</span><span class="sxs-lookup"><span data-stu-id="4ab2f-106">Instead, the computer stores an approximation of the number.</span></span> <span data-ttu-id="4ab2f-107">不同情况下，可能会使用不同的二进制位数来表示同一数字。</span><span class="sxs-lookup"><span data-stu-id="4ab2f-107">At different times, different numbers of binary digits may be used to represent the number.</span></span> <span data-ttu-id="4ab2f-108">当浮点数从一种表示形式转换为另一种表示形式时，该数字的最低有效位数可能稍有变化。</span><span class="sxs-lookup"><span data-stu-id="4ab2f-108">When a floating point number is converted from one representation to another representation, the least significant digits of that number may vary slightly.</span></span> <span data-ttu-id="4ab2f-109">当数字从一种类型强制转换为另一种类型时，通常会发生转换。</span><span class="sxs-lookup"><span data-stu-id="4ab2f-109">Conversion typically occurs when the number is cast from one type to another type.</span></span> <span data-ttu-id="4ab2f-110">无论转换是发生在数据库中表示数据库值的类型之间，还是发生在类型之间，都会产生差异。</span><span class="sxs-lookup"><span data-stu-id="4ab2f-110">The variation occurs whether the conversion occurs within a database, between types that represent database values, or between types.</span></span> <span data-ttu-id="4ab2f-111">由于这些变化，逻辑上相等的数字其最低有效位数可能会发生变化，从而导致它们具有不同的值。</span><span class="sxs-lookup"><span data-stu-id="4ab2f-111">Because of these changes, numbers that would logically be equal may have changes in their least-significant digits that cause them to have different values.</span></span> <span data-ttu-id="4ab2f-112">数字中的精度位数可能比预期的更大或更小。</span><span class="sxs-lookup"><span data-stu-id="4ab2f-112">The number of digits of precision in the number may be larger or smaller than expected.</span></span> <span data-ttu-id="4ab2f-113">将数字的格式设置为字符串时，可能不会显示预期值。</span><span class="sxs-lookup"><span data-stu-id="4ab2f-113">When formatted as a string, the number may not show the expected value.</span></span>  
  
 <span data-ttu-id="4ab2f-114">若要最大限度地减少这些影响，应在 numeric 类型之间使用您可用的最近似匹配。</span><span class="sxs-lookup"><span data-stu-id="4ab2f-114">To minimize these effects, you should use the closest match between numeric types that is available to you.</span></span> <span data-ttu-id="4ab2f-115">例如，如果您使用的是 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]，那么当您将实类型的 Transact-SQL 值转换为浮点类型的值时，精确数值可能发生变化。</span><span class="sxs-lookup"><span data-stu-id="4ab2f-115">For example, if you are working with [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], the exact numeric value may change if you convert a Transact-SQL value of real type to a value of float type.</span></span> <span data-ttu-id="4ab2f-116">在 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 中，将 <xref:System.Single> 转换为 <xref:System.Double> 还可能产生意外结果。</span><span class="sxs-lookup"><span data-stu-id="4ab2f-116">In the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], converting a <xref:System.Single> to a <xref:System.Double> may also produce unexpected results.</span></span> <span data-ttu-id="4ab2f-117">在这两种情况下，比较好的方法是使应用程序中的所有值都使用同一 numeric 类型。</span><span class="sxs-lookup"><span data-stu-id="4ab2f-117">In both of these cases, a good strategy is to make all the values in the application use the same numeric type.</span></span> <span data-ttu-id="4ab2f-118">您也可以使用固定精度的十进制类型，或者在使用浮点数之前将它们强制转换为固定精度的十进制类型。</span><span class="sxs-lookup"><span data-stu-id="4ab2f-118">You can also use a fixed-precision decimal type, or cast floating-point numbers to a fixed-precision decimal type before you work with them.</span></span>  
  
 <span data-ttu-id="4ab2f-119">若要使用相等比较来解决这些问题，请考虑对您的应用程序进行编码，以便忽略最低有效位数的变化。</span><span class="sxs-lookup"><span data-stu-id="4ab2f-119">To work around problems with equality comparison, consider coding your application so that variations in the least significant digits are ignored.</span></span> <span data-ttu-id="4ab2f-120">例如，用一个数减去另一个数，而不是通过比较，来了解两个数字是否相等。</span><span class="sxs-lookup"><span data-stu-id="4ab2f-120">For example, instead of comparing to see whether two numbers are equal, subtract one number from the other number.</span></span> <span data-ttu-id="4ab2f-121">如果差异在可接受舍入范围内，您的应用程序可以将这些数视为同一个数。</span><span class="sxs-lookup"><span data-stu-id="4ab2f-121">If the difference is within an acceptable margin of rounding, your application can treat the numbers as if they are the same.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ab2f-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ab2f-122">See Also</span></span>  
 [<span data-ttu-id="4ab2f-123">为何浮点数可能丢失精度</span><span class="sxs-lookup"><span data-stu-id="4ab2f-123">Why Floating-Point Numbers May Lose Precision</span></span>](http://msdn.microsoft.com/library/1acb1add-ac06-4134-a2fd-aff13d8c4c15)  
 [<span data-ttu-id="4ab2f-124">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="4ab2f-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
