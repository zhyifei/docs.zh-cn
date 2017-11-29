---
title: "保存和还原时区"
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
- restoring time zones
- deserialization [.NET Framework], time zones
- serialization [.NET Framework], time zones
- time zone objects [.NET Framework], restoring
- saving time zones
- time zone objects [.NET Framework], deserializing
- time zones [.NET Framework], saving
- time zones [.NET Framework], restoring
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 4028b310-e7ce-49d4-a646-1e83bfaf6f9d
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d4e04de61ed5636d0102af694220dce06c256751
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="saving-and-restoring-time-zones"></a><span data-ttu-id="940a8-102">保存和还原时区</span><span class="sxs-lookup"><span data-stu-id="940a8-102">Saving and restoring time zones</span></span>

<span data-ttu-id="940a8-103"><xref:System.TimeZoneInfo>类依赖于注册表以检索预定义的时区数据。</span><span class="sxs-lookup"><span data-stu-id="940a8-103">The <xref:System.TimeZoneInfo> class relies on the registry to retrieve predefined time zone data.</span></span> <span data-ttu-id="940a8-104">但是，注册表是动态的结构。</span><span class="sxs-lookup"><span data-stu-id="940a8-104">However, the registry is a dynamic structure.</span></span> <span data-ttu-id="940a8-105">此外，操作系统使用注册表包含时区信息主要是为了当前年度的处理时间调整和转换。</span><span class="sxs-lookup"><span data-stu-id="940a8-105">Additionally, the time zone information that the registry contains is used by the operating system primarily to handle time adjustments and conversions for the current year.</span></span> <span data-ttu-id="940a8-106">这样做有两个主要的影响的应用程序依赖于准确时区数据：</span><span class="sxs-lookup"><span data-stu-id="940a8-106">This has two major implications for applications that rely on accurate time zone data:</span></span>

* <span data-ttu-id="940a8-107">应用程序所需的时间区域可能未定义在注册表中，或它可能已重命名或从注册表中删除。</span><span class="sxs-lookup"><span data-stu-id="940a8-107">A time zone that is required by an application may not be defined in the registry, or it may have been renamed or removed from the registry.</span></span>

* <span data-ttu-id="940a8-108">在注册表中定义的时区可能缺少所需的历史时区转换的特定的调整规则有关的信息。</span><span class="sxs-lookup"><span data-stu-id="940a8-108">A time zone that is defined in the registry may lack information about the particular adjustment rules that are necessary for historical time zone conversions.</span></span>

<span data-ttu-id="940a8-109"><xref:System.TimeZoneInfo>类地址通过它进行序列化 （保存） 和反序列化 （还原） 的时区数据的支持这些限制。</span><span class="sxs-lookup"><span data-stu-id="940a8-109">The <xref:System.TimeZoneInfo> class addresses these limitations through its support for serialization (saving) and deserialization (restoring) of time zone data.</span></span>

## <a name="time-zone-serialization-and-deserialization"></a><span data-ttu-id="940a8-110">时区序列化和反序列化</span><span class="sxs-lookup"><span data-stu-id="940a8-110">Time zone serialization and deserialization</span></span>

<span data-ttu-id="940a8-111">保存和还原时区通过序列化和反序列化时区数据涉及到仅使用两个方法调用：</span><span class="sxs-lookup"><span data-stu-id="940a8-111">Saving and restoring a time zone by serializing and deserializing time zone data involves just two method calls:</span></span>

* <span data-ttu-id="940a8-112">您可以序列化<xref:System.TimeZoneInfo>通过调用该对象的对象<xref:System.TimeZoneInfo.ToSerializedString%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="940a8-112">You can serialize a <xref:System.TimeZoneInfo> object by calling that object's <xref:System.TimeZoneInfo.ToSerializedString%2A> method.</span></span> <span data-ttu-id="940a8-113">该方法不采用任何参数，并返回一个字符串，包含时区信息。</span><span class="sxs-lookup"><span data-stu-id="940a8-113">The method takes no parameters and returns a string that contains time zone information.</span></span>

* <span data-ttu-id="940a8-114">可以反序列化<xref:System.TimeZoneInfo>中通过将传递到该字符串的序列化字符串对象`static`(`Shared`在 Visual Basic 中)<xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="940a8-114">You can deserialize a <xref:System.TimeZoneInfo> object from a serialized string by passing that string to the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=nameWithType> method.</span></span>

## <a name="serialization-and-deserialization-scenarios"></a><span data-ttu-id="940a8-115">序列化和反序列化方案</span><span class="sxs-lookup"><span data-stu-id="940a8-115">Serialization and deserialization scenarios</span></span>

<span data-ttu-id="940a8-116">能够保存 （或序列化）<xref:System.TimeZoneInfo>对象，为字符串以及还原 （或反序列化） 它以供将来使用会增加该实用程序和灵活性<xref:System.TimeZoneInfo>类。</span><span class="sxs-lookup"><span data-stu-id="940a8-116">The ability to save (or serialize) a <xref:System.TimeZoneInfo> object to a string and to restore (or deserialize) it for later use increases both the utility and the flexibility of the <xref:System.TimeZoneInfo> class.</span></span> <span data-ttu-id="940a8-117">本部分介绍一些序列化和反序列化是最有用的情况。</span><span class="sxs-lookup"><span data-stu-id="940a8-117">This section examines some of the situations in which serialization and deserialization are most useful.</span></span>

### <a name="serializing-and-deserializing-time-zone-data-in-an-application"></a><span data-ttu-id="940a8-118">序列化和反序列化应用程序中的时区数据</span><span class="sxs-lookup"><span data-stu-id="940a8-118">Serializing and deserializing time zone data in an application</span></span>

<span data-ttu-id="940a8-119">需要时，可以从字符串还原序列化的时区。</span><span class="sxs-lookup"><span data-stu-id="940a8-119">A serialized time zone can be restored from a string when it is needed.</span></span> <span data-ttu-id="940a8-120">如果从注册表检索时区不能正确转换的日期和时间在特定日期范围内的，应用程序可以这样做。</span><span class="sxs-lookup"><span data-stu-id="940a8-120">An application might do this if the time zone retrieved from the registry is unable to correctly convert a date and time within a particular date range.</span></span> <span data-ttu-id="940a8-121">例如，Windows XP 注册表中的时区数据支持一个调整规则，通常在 Windows Vista 注册表中定义的时区提供信息讨论了两次调整规则。</span><span class="sxs-lookup"><span data-stu-id="940a8-121">For example, time zone data in the Windows XP registry supports a single adjustment rule, while time zones defined in the Windows Vista registry typically provide information about two adjustment rules.</span></span> <span data-ttu-id="940a8-122">这意味着历史时间转换可能不准确。</span><span class="sxs-lookup"><span data-stu-id="940a8-122">This means that historical time conversions may be inaccurate.</span></span> <span data-ttu-id="940a8-123">序列化和反序列化的时区数据可以处理此限制。</span><span class="sxs-lookup"><span data-stu-id="940a8-123">Serialization and deserialization of time zone data can handle this limitation.</span></span>

<span data-ttu-id="940a8-124">在下面的示例中，自定义<xref:System.TimeZoneInfo>没有调整规则的类定义来表示美国美国东部标准时间区域从 1883年到 1917 之前在美国国内夏时制的简介。</span><span class="sxs-lookup"><span data-stu-id="940a8-124">In the following example, a custom <xref:System.TimeZoneInfo> class that has no adjustment rules is defined to represent the U.S. Eastern Standard Time zone from 1883 to 1917, before the introduction of daylight saving time in the United States.</span></span> <span data-ttu-id="940a8-125">自定义时区的序列化具有全局作用域的变量中。</span><span class="sxs-lookup"><span data-stu-id="940a8-125">The custom time zone is serialized in a variable that has global scope.</span></span> <span data-ttu-id="940a8-126">时区转换方法， `ConvertUtcTime`，将传递协调通用时 (UTC) 时间，它将转换。</span><span class="sxs-lookup"><span data-stu-id="940a8-126">The time zone conversion method, `ConvertUtcTime`, is passed Coordinated Universal Time (UTC) times to convert.</span></span> <span data-ttu-id="940a8-127">如果日期和时间发生在 1917 年或更早版本，自定义的东部标准时区还原从序列化的字符串，并替换从注册表检索的时区。</span><span class="sxs-lookup"><span data-stu-id="940a8-127">If the date and time occurs in 1917 or earlier, the custom Eastern Standard Time zone is restored from a serialized string and replaces the time zone retrieved from the registry.</span></span>

[!code-csharp[System.TimeZone2.Serialization.1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/cs/Serialization.cs#1)]
[!code-vb[System.TimeZone2.Serialization.1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/vb/Serialization.vb#1)]

### <a name="handling-time-zone-exceptions"></a><span data-ttu-id="940a8-128">处理时区异常</span><span class="sxs-lookup"><span data-stu-id="940a8-128">Handling time zone exceptions</span></span>

<span data-ttu-id="940a8-129">由于注册表是动态的结构，其内容可能会发生意外或有意修改。</span><span class="sxs-lookup"><span data-stu-id="940a8-129">Because the registry is a dynamic structure, its contents are subject to accidental or deliberate modification.</span></span> <span data-ttu-id="940a8-130">这意味着同一时区，应在注册表中定义和所需应用程序，才能成功执行可能不存在。</span><span class="sxs-lookup"><span data-stu-id="940a8-130">This means that a time zone that should be defined in the registry and that is required for an application to execute successfully may be absent.</span></span> <span data-ttu-id="940a8-131">若不支持时区序列化和反序列化，则只能选择但若要处理生成<xref:System.TimeZoneNotFoundException>通过结束应用程序。</span><span class="sxs-lookup"><span data-stu-id="940a8-131">Without support for time zone serialization and deserialization, you have little choice but to handle the resulting <xref:System.TimeZoneNotFoundException> by ending the application.</span></span> <span data-ttu-id="940a8-132">但是，通过使用时区序列化和反序列化，你可以处理意外<xref:System.TimeZoneNotFoundException>通过还原所需的时间区域，从序列化的字符串和应用程序将继续运行。</span><span class="sxs-lookup"><span data-stu-id="940a8-132">However, by using time zone serialization and deserialization, you can handle an unexpected <xref:System.TimeZoneNotFoundException> by restoring the required time zone from a serialized string, and the application will continue to run.</span></span>

<span data-ttu-id="940a8-133">下面的示例创建和序列化自定义的中部标准时区。</span><span class="sxs-lookup"><span data-stu-id="940a8-133">The following example creates and serializes a custom Central Standard Time zone.</span></span> <span data-ttu-id="940a8-134">它会尝试从注册表检索中部标准时区。</span><span class="sxs-lookup"><span data-stu-id="940a8-134">It then tries to retrieve the Central Standard Time zone from the registry.</span></span> <span data-ttu-id="940a8-135">如果检索操作引发或者<xref:System.TimeZoneNotFoundException>或<xref:System.InvalidTimeZoneException>，异常处理程序反序列化时区。</span><span class="sxs-lookup"><span data-stu-id="940a8-135">If the retrieval operation throws either a <xref:System.TimeZoneNotFoundException> or an <xref:System.InvalidTimeZoneException>, the exception handler deserializes the time zone.</span></span>

[!code-csharp[System.TimeZone2.Serialization.2#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/cs/Serialization2.cs#1)]
[!code-vb[System.TimeZone2.Serialization.2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/vb/Serialization2.vb#1)]

### <a name="storing-a-serialized-string-and-restoring-it-when-needed"></a><span data-ttu-id="940a8-136">将序列化的字符串存储和还原在需要时</span><span class="sxs-lookup"><span data-stu-id="940a8-136">Storing a serialized string and restoring it when needed</span></span>

<span data-ttu-id="940a8-137">前面的示例包含存储为一个字符串变量的时区信息，且已在需要时还原。</span><span class="sxs-lookup"><span data-stu-id="940a8-137">The previous examples have stored time zone information to a string variable and restored it when needed.</span></span> <span data-ttu-id="940a8-138">但是，包含区域信息可以本身存储在某些存储介质，例如外部文件，资源文件的序列化的时间的字符串嵌入在应用程序或注册表。</span><span class="sxs-lookup"><span data-stu-id="940a8-138">However, the string that contains serialized time zone information can itself be stored in some storage medium, such as an external file, a resource file embedded in the application, or the registry.</span></span> <span data-ttu-id="940a8-139">（请注意，应除了注册表中的系统的时区密钥存储有关自定义时区信息。）</span><span class="sxs-lookup"><span data-stu-id="940a8-139">(Note that information about custom time zones should be stored apart from the system's time zone keys in the registry.)</span></span>

<span data-ttu-id="940a8-140">从应用程序本身，在这种方式中存储的序列化的时区字符串还分隔时区创建例程。</span><span class="sxs-lookup"><span data-stu-id="940a8-140">Storing a serialized time zone string in this manner also separates the time zone creation routine from the application itself.</span></span> <span data-ttu-id="940a8-141">例如，时区创建例程可以执行并创建数据文件，其中包含应用程序可以使用的历史时区信息。</span><span class="sxs-lookup"><span data-stu-id="940a8-141">For example, a time zone creation routine can execute and create a data file that contains historical time zone information that an application can use.</span></span> <span data-ttu-id="940a8-142">数据文件便可安装应用程序后，可以打开和一个或多个其时区可以反序列化应用程序需要它们时。</span><span class="sxs-lookup"><span data-stu-id="940a8-142">The data file can be then be installed with the application, and it can be opened and one or more of its time zones can be deserialized when the application requires them.</span></span>

<span data-ttu-id="940a8-143">使用嵌入的资源来存储序列化的时区数据示例，请参阅[如何： 将时区保存到嵌入的资源](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)和[如何： 从嵌入的资源还原时区](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)。</span><span class="sxs-lookup"><span data-stu-id="940a8-143">For an example that uses an embedded resource to store serialized time zone data, see [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) and [How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="940a8-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="940a8-144">See also</span></span>

[<span data-ttu-id="940a8-145">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="940a8-145">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
