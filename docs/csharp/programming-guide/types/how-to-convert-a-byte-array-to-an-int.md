---
title: "如何：将字节数组转换为 int（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- conversions [C#], byte array to int
- byte arrays [C#], converting to int
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ee51cd94e961c7274286c812cb6900d26c6ce033
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-a-byte-array-to-an-int-c-programming-guide"></a><span data-ttu-id="de40c-102">如何：将字节数组转换为 int（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="de40c-102">How to: Convert a byte Array to an int (C# Programming Guide)</span></span>
<span data-ttu-id="de40c-103">此示例演示如何使用 <xref:System.BitConverter> 类将字节数组转换为 [int](../../../csharp/language-reference/keywords/int.md) 然后又转换回字节数组。</span><span class="sxs-lookup"><span data-stu-id="de40c-103">This example shows you how to use the <xref:System.BitConverter> class to convert an array of bytes to an [int](../../../csharp/language-reference/keywords/int.md) and back to an array of bytes.</span></span> <span data-ttu-id="de40c-104">例如，在从网络读取字节之后，可能需要将字节转换为内置数据类型。</span><span class="sxs-lookup"><span data-stu-id="de40c-104">You may have to convert from bytes to a built-in data type after you read bytes off the network, for example.</span></span> <span data-ttu-id="de40c-105">除了示例中的 [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) 方法之外，下表还列出了 <xref:System.BitConverter> 类中将字节（来自字节数组）转换为其他内置类型的方法。</span><span class="sxs-lookup"><span data-stu-id="de40c-105">In addition to the [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) method in the example, the following table lists methods in the <xref:System.BitConverter> class that convert bytes (from an array of bytes) to other built-in types.</span></span>  
  
|<span data-ttu-id="de40c-106">返回类型</span><span class="sxs-lookup"><span data-stu-id="de40c-106">Type returned</span></span>|<span data-ttu-id="de40c-107">方法</span><span class="sxs-lookup"><span data-stu-id="de40c-107">Method</span></span>|  
|-------------------|------------|  
|`bool`|<span data-ttu-id="de40c-108">[ToBoolean(Byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="de40c-108">[ToBoolean(Byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))</span></span>|  
|`char`|<span data-ttu-id="de40c-109">[ToChar(Byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="de40c-109">[ToChar(Byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))</span></span>|  
|`double`|<span data-ttu-id="de40c-110">[ToDouble(Byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="de40c-110">[ToDouble(Byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))</span></span>|  
|`short`|<span data-ttu-id="de40c-111">[ToInt16(Byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="de40c-111">[ToInt16(Byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))</span></span>|  
|`int`|<span data-ttu-id="de40c-112">[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="de40c-112">[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))</span></span>|  
|`long`|<span data-ttu-id="de40c-113">[ToInt64(Byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="de40c-113">[ToInt64(Byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))</span></span>|  
|`float`|<span data-ttu-id="de40c-114">[ToSingle(Byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="de40c-114">[ToSingle(Byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))</span></span>|  
|`ushort`|<span data-ttu-id="de40c-115">[ToUInt16(Byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="de40c-115">[ToUInt16(Byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))</span></span>|  
|`uint`|<span data-ttu-id="de40c-116">[ToUInt32(Byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="de40c-116">[ToUInt32(Byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))</span></span>|  
|`ulong`|<span data-ttu-id="de40c-117">[ToUInt64(Byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="de40c-117">[ToUInt64(Byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))</span></span>|  
  
## <a name="example"></a><span data-ttu-id="de40c-118">示例</span><span class="sxs-lookup"><span data-stu-id="de40c-118">Example</span></span>  
 <span data-ttu-id="de40c-119">此示例初始化字节数组，并在计算机体系结构为 little-endian（即首先存储最低有效字节）的情况下反转数组，然后调用 [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) 方法以将数组中的四个字节转换为 `int`。</span><span class="sxs-lookup"><span data-stu-id="de40c-119">This example initializes an array of bytes, reverses the array if the computer architecture is little-endian (that is, the least significant byte is stored first), and then calls the [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) method to convert four bytes in the array to an `int`.</span></span> <span data-ttu-id="de40c-120">[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) 的第二个参数指定字节数组的起始索引。</span><span class="sxs-lookup"><span data-stu-id="de40c-120">The second argument to [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) specifies the start index of the array of bytes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de40c-121">输出可能会根据计算机体系结构的 endian 设置而不同。</span><span class="sxs-lookup"><span data-stu-id="de40c-121">The output may differ depending on the endianess of your computer's architecture.</span></span>  
  
 [!code-csharp[csProgGuideTypes#22](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="de40c-122">示例</span><span class="sxs-lookup"><span data-stu-id="de40c-122">Example</span></span>  
 <span data-ttu-id="de40c-123">在本示例中，将调用 <xref:System.BitConverter> 类的 <xref:System.BitConverter.GetBytes%28System.Int32%29> 方法，将 `int` 转换为字节数组。</span><span class="sxs-lookup"><span data-stu-id="de40c-123">In this example, the <xref:System.BitConverter.GetBytes%28System.Int32%29> method of the <xref:System.BitConverter> class is called to convert an `int` to an array of bytes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de40c-124">输出可能会根据计算机体系结构的 endian 设置而不同。</span><span class="sxs-lookup"><span data-stu-id="de40c-124">The output may differ depending on the endianess of your computer's architecture.</span></span>  
  
 [!code-csharp[csProgGuideTypes#23](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="de40c-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de40c-125">See Also</span></span>  
 <xref:System.BitConverter>  
 <xref:System.BitConverter.IsLittleEndian>  
 [<span data-ttu-id="de40c-126">类型</span><span class="sxs-lookup"><span data-stu-id="de40c-126">Types</span></span>](../../../csharp/programming-guide/types/index.md)
