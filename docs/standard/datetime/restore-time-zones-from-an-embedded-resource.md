---
title: "如何： 从嵌入的资源还原时区"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: db4f2ae40d25795b0e5f75ac3612f45834043dfa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a><span data-ttu-id="9e45b-102">如何： 从嵌入的资源还原时区</span><span class="sxs-lookup"><span data-stu-id="9e45b-102">How to: Restore time zones from an embedded resource</span></span>

<span data-ttu-id="9e45b-103">本主题介绍如何还原已保存的资源文件中的时区。</span><span class="sxs-lookup"><span data-stu-id="9e45b-103">This topic describes how to restore time zones that have been saved in a resource file.</span></span> <span data-ttu-id="9e45b-104">有关信息和有关保存时区的说明，请参阅[如何： 将时区保存到嵌入的资源](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)。</span><span class="sxs-lookup"><span data-stu-id="9e45b-104">For information and instructions about saving time zones, see [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span></span>

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a><span data-ttu-id="9e45b-105">若要反序列化中嵌入的资源的 TimeZoneInfo 对象</span><span class="sxs-lookup"><span data-stu-id="9e45b-105">To deserialize a TimeZoneInfo object from an embedded resource</span></span>

1. <span data-ttu-id="9e45b-106">如果要检索时区不是自定义的时区，尝试通过使用下面实例<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="9e45b-106">If the time zone to be retrieved is not a custom time zone, try to instantiate it by using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span>

2. <span data-ttu-id="9e45b-107">实例化<xref:System.Resources.ResourceManager>通过将传递对包含资源文件的程序集的引用以及嵌入式的资源文件的完全限定的名称的对象。</span><span class="sxs-lookup"><span data-stu-id="9e45b-107">Instantiate a <xref:System.Resources.ResourceManager> object by passing the fully qualified name of the embedded resource file and a reference to the assembly that contains the resource file.</span></span>

   <span data-ttu-id="9e45b-108">如果无法确定嵌入式的资源文件的完全限定的名称，使用[Ildasm.exe （IL 反汇编程序）](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)来检查程序集的清单。</span><span class="sxs-lookup"><span data-stu-id="9e45b-108">If you cannot determine the fully qualified name of the embedded resource file, use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's manifest.</span></span> <span data-ttu-id="9e45b-109">`.mresource`条目标识的资源。</span><span class="sxs-lookup"><span data-stu-id="9e45b-109">An `.mresource` entry identifies the resource.</span></span> <span data-ttu-id="9e45b-110">在示例中，该资源的完全限定的名称是`SerializeTimeZoneData.SerializedTimeZones`。</span><span class="sxs-lookup"><span data-stu-id="9e45b-110">In the example, the resource's fully qualified name is `SerializeTimeZoneData.SerializedTimeZones`.</span></span>

   <span data-ttu-id="9e45b-111">如果包含时区实例化代码相同的程序集中嵌入资源文件，则可以通过调用来检索对它的引用`static`(`Shared`在 Visual Basic 中)<xref:System.Reflection.Assembly.GetExecutingAssembly%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="9e45b-111">If the resource file is embedded in the same assembly that contains the time zone instantiation code, you can retrieve a reference to it by calling the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method.</span></span>

3. <span data-ttu-id="9e45b-112">如果调用<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>方法失败，或如果要实例化自定义的时区，检索一个字符串，通过调用包含序列化的时区<xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="9e45b-112">If the call to the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method fails, or if a custom time zone is to be instantiated, retrieve a string that contains the serialized time zone by calling the <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="9e45b-113">通过调用时区数据反序列化<xref:System.TimeZoneInfo.FromSerializedString%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="9e45b-113">Deserialize the time zone data by calling the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="example"></a><span data-ttu-id="9e45b-114">示例</span><span class="sxs-lookup"><span data-stu-id="9e45b-114">Example</span></span>

<span data-ttu-id="9e45b-115">下面的示例进行反序列化<xref:System.TimeZoneInfo>嵌入.NET XML 资源文件中存储的对象。</span><span class="sxs-lookup"><span data-stu-id="9e45b-115">The following example deserializes a <xref:System.TimeZoneInfo> object stored in an embedded .NET XML resource file.</span></span>

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

<span data-ttu-id="9e45b-116">此代码演示异常处理来确保<xref:System.TimeZoneInfo>应用程序所需的对象是否存在。</span><span class="sxs-lookup"><span data-stu-id="9e45b-116">This code illustrates exception handling to ensure that a <xref:System.TimeZoneInfo> object required by the application is present.</span></span> <span data-ttu-id="9e45b-117">它首先尝试实例化<xref:System.TimeZoneInfo>对象通过检索从注册表使用<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="9e45b-117">It first tries to instantiate a <xref:System.TimeZoneInfo> object by retrieving it from the registry using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span> <span data-ttu-id="9e45b-118">如果时区不能实例化，此代码将检索它从嵌入的资源文件。</span><span class="sxs-lookup"><span data-stu-id="9e45b-118">If the time zone cannot be instantiated, the code retrieves it from the embedded resource file.</span></span>

<span data-ttu-id="9e45b-119">因为自定义时区的数据 (通过使用实例化时区<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>方法) 不存储在注册表中，代码不调用<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>来实例化 Palmer，南极洲时区。</span><span class="sxs-lookup"><span data-stu-id="9e45b-119">Because data for custom time zones (time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method) are not stored in the registry, the code does not call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> to instantiate the time zone for Palmer, Antarctica.</span></span> <span data-ttu-id="9e45b-120">相反，它立即查找到嵌入的资源文件，以检索一个字符串，包含时区的数据，然后才能调用<xref:System.TimeZoneInfo.FromSerializedString%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="9e45b-120">Instead, it immediately looks to the embedded resource file to retrieve a string that contains the time zone's data before it calls the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="9e45b-121">编译代码</span><span class="sxs-lookup"><span data-stu-id="9e45b-121">Compiling the code</span></span>

<span data-ttu-id="9e45b-122">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="9e45b-122">This example requires:</span></span>

* <span data-ttu-id="9e45b-123">对 System.Windows.Forms.dll 和 System.Core.dll 的引用无法添加到项目。</span><span class="sxs-lookup"><span data-stu-id="9e45b-123">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="9e45b-124">将导入以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="9e45b-124">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="9e45b-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e45b-125">See also</span></span>

<span data-ttu-id="9e45b-126">[日期、 时间和时区](../../../docs/standard/datetime/index.md)
[时区概述](../../../docs/standard/datetime/time-zone-overview.md)
[如何： 将时区保存到嵌入的资源](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)</span><span class="sxs-lookup"><span data-stu-id="9e45b-126">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Time zone overview](../../../docs/standard/datetime/time-zone-overview.md)
[How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)</span></span>
