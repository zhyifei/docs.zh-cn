---
title: 如何：将字节数组转换为 int - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], byte array to int
- byte arrays [C#], converting to int
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
ms.openlocfilehash: 82ed87bbcbc741695afc49069c413ae440bd147b
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423552"
---
# <a name="how-to-convert-a-byte-array-to-an-int-c-programming-guide"></a><span data-ttu-id="3fbb0-102">如何：将字节数组转换为 int（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="3fbb0-102">How to: Convert a byte Array to an int (C# Programming Guide)</span></span>
<span data-ttu-id="3fbb0-103">此示例演示如何使用 <xref:System.BitConverter> 类将字节数组转换为 [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) 然后又转换回字节数组。</span><span class="sxs-lookup"><span data-stu-id="3fbb0-103">This example shows you how to use the <xref:System.BitConverter> class to convert an array of bytes to an [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) and back to an array of bytes.</span></span> <span data-ttu-id="3fbb0-104">例如，在从网络读取字节之后，可能需要将字节转换为内置数据类型。</span><span class="sxs-lookup"><span data-stu-id="3fbb0-104">You may have to convert from bytes to a built-in data type after you read bytes off the network, for example.</span></span> <span data-ttu-id="3fbb0-105">除了示例中的 [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) 方法之外，下表还列出了 <xref:System.BitConverter> 类中将字节（来自字节数组）转换为其他内置类型的方法。</span><span class="sxs-lookup"><span data-stu-id="3fbb0-105">In addition to the [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) method in the example, the following table lists methods in the <xref:System.BitConverter> class that convert bytes (from an array of bytes) to other built-in types.</span></span>  
  
|<span data-ttu-id="3fbb0-106">返回类型</span><span class="sxs-lookup"><span data-stu-id="3fbb0-106">Type returned</span></span>|<span data-ttu-id="3fbb0-107">方法</span><span class="sxs-lookup"><span data-stu-id="3fbb0-107">Method</span></span>|  
|-------------------|------------|  
|`bool`|<span data-ttu-id="3fbb0-108">[ToBoolean(Byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="3fbb0-108">[ToBoolean(Byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))</span></span>|  
|`char`|<span data-ttu-id="3fbb0-109">[ToChar(Byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="3fbb0-109">[ToChar(Byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))</span></span>|  
|`double`|<span data-ttu-id="3fbb0-110">[ToDouble(Byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="3fbb0-110">[ToDouble(Byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))</span></span>|  
|`short`|<span data-ttu-id="3fbb0-111">[ToInt16(Byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="3fbb0-111">[ToInt16(Byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))</span></span>|  
|`int`|<span data-ttu-id="3fbb0-112">[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="3fbb0-112">[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))</span></span>|  
|`long`|<span data-ttu-id="3fbb0-113">[ToInt64(Byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="3fbb0-113">[ToInt64(Byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))</span></span>|  
|`float`|<span data-ttu-id="3fbb0-114">[ToSingle(Byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="3fbb0-114">[ToSingle(Byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))</span></span>|  
|`ushort`|<span data-ttu-id="3fbb0-115">[ToUInt16(Byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="3fbb0-115">[ToUInt16(Byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))</span></span>|  
|`uint`|<span data-ttu-id="3fbb0-116">[ToUInt32(Byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="3fbb0-116">[ToUInt32(Byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))</span></span>|  
|`ulong`|<span data-ttu-id="3fbb0-117">[ToUInt64(Byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="3fbb0-117">[ToUInt64(Byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3fbb0-118">示例</span><span class="sxs-lookup"><span data-stu-id="3fbb0-118">Example</span></span>  
 <span data-ttu-id="3fbb0-119">此示例初始化字节数组，并在计算机体系结构为 little-endian（即首先存储最低有效字节）的情况下反转数组，然后调用 [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) 方法以将数组中的四个字节转换为 `int`。</span><span class="sxs-lookup"><span data-stu-id="3fbb0-119">This example initializes an array of bytes, reverses the array if the computer architecture is little-endian (that is, the least significant byte is stored first), and then calls the [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) method to convert four bytes in the array to an `int`.</span></span> <span data-ttu-id="3fbb0-120">[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) 的第二个参数指定字节数组的起始索引。</span><span class="sxs-lookup"><span data-stu-id="3fbb0-120">The second argument to [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) specifies the start index of the array of bytes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fbb0-121">输出可能会根据计算机体系结构的 endian 设置而不同。</span><span class="sxs-lookup"><span data-stu-id="3fbb0-121">The output may differ depending on the endianess of your computer's architecture.</span></span>  
  
 [!code-csharp[csProgGuideTypes#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#22)]  
  
## <a name="example"></a><span data-ttu-id="3fbb0-122">示例</span><span class="sxs-lookup"><span data-stu-id="3fbb0-122">Example</span></span>  
 <span data-ttu-id="3fbb0-123">在本示例中，将调用 <xref:System.BitConverter> 类的 <xref:System.BitConverter.GetBytes%28System.Int32%29> 方法，将 `int` 转换为字节数组。</span><span class="sxs-lookup"><span data-stu-id="3fbb0-123">In this example, the <xref:System.BitConverter.GetBytes%28System.Int32%29> method of the <xref:System.BitConverter> class is called to convert an `int` to an array of bytes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fbb0-124">输出可能会根据计算机体系结构的 endian 设置而不同。</span><span class="sxs-lookup"><span data-stu-id="3fbb0-124">The output may differ depending on the endianess of your computer's architecture.</span></span>  
  
 [!code-csharp[csProgGuideTypes#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#23)]  
  
## <a name="see-also"></a><span data-ttu-id="3fbb0-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="3fbb0-125">See also</span></span>

- <xref:System.BitConverter>
- <xref:System.BitConverter.IsLittleEndian>
- [<span data-ttu-id="3fbb0-126">类型</span><span class="sxs-lookup"><span data-stu-id="3fbb0-126">Types</span></span>](../../../csharp/programming-guide/types/index.md)
