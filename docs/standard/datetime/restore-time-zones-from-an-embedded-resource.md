---
title: 如何：从嵌入的资源还原时区
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
ms.openlocfilehash: cd2119d6d22f3f676b7167ed545aeb058123cfb5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122194"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a><span data-ttu-id="7a718-102">如何：从嵌入的资源还原时区</span><span class="sxs-lookup"><span data-stu-id="7a718-102">How to: Restore time zones from an embedded resource</span></span>

<span data-ttu-id="7a718-103">本主题介绍如何还原已保存到资源文件中的时区。</span><span class="sxs-lookup"><span data-stu-id="7a718-103">This topic describes how to restore time zones that have been saved in a resource file.</span></span> <span data-ttu-id="7a718-104">有关保存时区的信息和说明，请参阅[如何：将时区保存到嵌入的资源](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)。</span><span class="sxs-lookup"><span data-stu-id="7a718-104">For information and instructions about saving time zones, see [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span></span>

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a><span data-ttu-id="7a718-105">反序列化嵌入资源中的 TimeZoneInfo 对象</span><span class="sxs-lookup"><span data-stu-id="7a718-105">To deserialize a TimeZoneInfo object from an embedded resource</span></span>

1. <span data-ttu-id="7a718-106">如果要检索的时区不是自定义时区，请尝试使用 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 方法对其进行实例化。</span><span class="sxs-lookup"><span data-stu-id="7a718-106">If the time zone to be retrieved is not a custom time zone, try to instantiate it by using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span>

2. <span data-ttu-id="7a718-107">通过传递嵌入资源文件的完全限定名和对包含资源文件的程序集的引用来实例化 <xref:System.Resources.ResourceManager> 对象。</span><span class="sxs-lookup"><span data-stu-id="7a718-107">Instantiate a <xref:System.Resources.ResourceManager> object by passing the fully qualified name of the embedded resource file and a reference to the assembly that contains the resource file.</span></span>

   <span data-ttu-id="7a718-108">如果无法确定嵌入资源文件的完全限定名称，请使用[Ildasm （IL 拆装器）](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)检查程序集的清单。</span><span class="sxs-lookup"><span data-stu-id="7a718-108">If you cannot determine the fully qualified name of the embedded resource file, use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's manifest.</span></span> <span data-ttu-id="7a718-109">`.mresource` 项标识资源。</span><span class="sxs-lookup"><span data-stu-id="7a718-109">An `.mresource` entry identifies the resource.</span></span> <span data-ttu-id="7a718-110">在此示例中，资源的完全限定名称是 `SerializeTimeZoneData.SerializedTimeZones`。</span><span class="sxs-lookup"><span data-stu-id="7a718-110">In the example, the resource's fully qualified name is `SerializeTimeZoneData.SerializedTimeZones`.</span></span>

   <span data-ttu-id="7a718-111">如果资源文件嵌入到包含时区实例化代码的同一程序集中，则可以通过调用 `static` （`Shared` Visual Basic 中） <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> 方法来检索对该文件的引用。</span><span class="sxs-lookup"><span data-stu-id="7a718-111">If the resource file is embedded in the same assembly that contains the time zone instantiation code, you can retrieve a reference to it by calling the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method.</span></span>

3. <span data-ttu-id="7a718-112">如果对 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 方法的调用失败，或者如果要实例化自定义时区，则通过调用 <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> 方法来检索包含序列化时区的字符串。</span><span class="sxs-lookup"><span data-stu-id="7a718-112">If the call to the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method fails, or if a custom time zone is to be instantiated, retrieve a string that contains the serialized time zone by calling the <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="7a718-113">通过调用 <xref:System.TimeZoneInfo.FromSerializedString%2A> 方法反序列化时区数据。</span><span class="sxs-lookup"><span data-stu-id="7a718-113">Deserialize the time zone data by calling the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="example"></a><span data-ttu-id="7a718-114">示例</span><span class="sxs-lookup"><span data-stu-id="7a718-114">Example</span></span>

<span data-ttu-id="7a718-115">下面的示例对嵌入的 .NET XML 资源文件中存储的 <xref:System.TimeZoneInfo> 对象进行反序列化。</span><span class="sxs-lookup"><span data-stu-id="7a718-115">The following example deserializes a <xref:System.TimeZoneInfo> object stored in an embedded .NET XML resource file.</span></span>

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

<span data-ttu-id="7a718-116">此代码演示了异常处理，以确保应用程序所需的 <xref:System.TimeZoneInfo> 对象存在。</span><span class="sxs-lookup"><span data-stu-id="7a718-116">This code illustrates exception handling to ensure that a <xref:System.TimeZoneInfo> object required by the application is present.</span></span> <span data-ttu-id="7a718-117">它首先尝试使用 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 方法通过从注册表中检索 <xref:System.TimeZoneInfo> 对象来实例化该对象。</span><span class="sxs-lookup"><span data-stu-id="7a718-117">It first tries to instantiate a <xref:System.TimeZoneInfo> object by retrieving it from the registry using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span> <span data-ttu-id="7a718-118">如果无法实例化时区，则代码会从嵌入的资源文件中检索该时区。</span><span class="sxs-lookup"><span data-stu-id="7a718-118">If the time zone cannot be instantiated, the code retrieves it from the embedded resource file.</span></span>

<span data-ttu-id="7a718-119">由于自定义时区（使用 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 方法实例化的时区）的数据不会存储在注册表中，因此该代码不会调用 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 来实例化 Palmer，南极洲的时区。</span><span class="sxs-lookup"><span data-stu-id="7a718-119">Because data for custom time zones (time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method) are not stored in the registry, the code does not call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> to instantiate the time zone for Palmer, Antarctica.</span></span> <span data-ttu-id="7a718-120">相反，它会在调用 <xref:System.TimeZoneInfo.FromSerializedString%2A> 方法之前，立即查看嵌入的资源文件以检索包含时区数据的字符串。</span><span class="sxs-lookup"><span data-stu-id="7a718-120">Instead, it immediately looks to the embedded resource file to retrieve a string that contains the time zone's data before it calls the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="7a718-121">编译代码</span><span class="sxs-lookup"><span data-stu-id="7a718-121">Compiling the code</span></span>

<span data-ttu-id="7a718-122">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="7a718-122">This example requires:</span></span>

- <span data-ttu-id="7a718-123">对该项目的引用将被添加到该项目中的。</span><span class="sxs-lookup"><span data-stu-id="7a718-123">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

- <span data-ttu-id="7a718-124">导入以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="7a718-124">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="7a718-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a718-125">See also</span></span>

- [<span data-ttu-id="7a718-126">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="7a718-126">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="7a718-127">时区概述</span><span class="sxs-lookup"><span data-stu-id="7a718-127">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="7a718-128">如何：将时区保存到嵌入的资源中</span><span class="sxs-lookup"><span data-stu-id="7a718-128">How to: Save time zones to an embedded resource</span></span>](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
