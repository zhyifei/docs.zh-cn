---
title: 二进制序列化
ms.date: 01/02/2018
helpviewer_keywords:
- binary serialization
- serialization, about serialization
- deserialization
- binary serialization, about serialization
- binary serialization, .net core serialization
- serialization, cross-framework
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
author: ViktorHofer
ms.openlocfilehash: 9df9b73a1a1347b952d76b76c9058578f5e9f401
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901042"
---
# <a name="binary-serialization"></a><span data-ttu-id="e7bf6-102">二进制序列化</span><span class="sxs-lookup"><span data-stu-id="e7bf6-102">Binary serialization</span></span>

<span data-ttu-id="e7bf6-103">可以将序列化定义为一个将对象状态存储到存储介质的过程。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-103">Serialization can be defined as the process of storing the state of an object to a storage medium.</span></span> <span data-ttu-id="e7bf6-104">在这个过程中，对象的公共字段和私有字段以及类（包括含有该类的程序集）的名称，将转换成字节流，而字节流接着将写入数据流。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-104">During this process, the public and private fields of the object and the name of the class, including the assembly containing the class, are converted to a stream of bytes, which is then written to a data stream.</span></span> <span data-ttu-id="e7bf6-105">随后对该对象进行反序列化时，将创建原始对象的准确克隆。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-105">When the object is subsequently deserialized, an exact clone of the original object is created.</span></span>

<span data-ttu-id="e7bf6-106">在面向对象的环境中实现序列化机制时，必须多在易用性与灵活性之间做出权衡。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-106">When implementing a serialization mechanism in an object-oriented environment, you have to make a number of tradeoffs between ease of use and flexibility.</span></span> <span data-ttu-id="e7bf6-107">很大程度上，这个过程可以自动完成，但前提是您对该过程拥有足够的控制权。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-107">The process can be automated to a large extent, provided you are given sufficient control over the process.</span></span> <span data-ttu-id="e7bf6-108">例如，如果简单的二进制序列化不足，或者可能有特定原因决定需要对类中的哪些字段进行序列化，可能就会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-108">For example, situations may arise where simple binary serialization is not sufficient, or there might be a specific reason to decide which fields in a class need to be serialized.</span></span> <span data-ttu-id="e7bf6-109">以下章节验证了随 .NET Framework 一起提供的可靠序列化机制，并强调了根据需要自定义该过程所能使用的一些重要功能。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-109">The following sections examine the robust serialization mechanism provided with .NET and highlight a number of important features that allow you to customize the process to meet your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="e7bf6-110">如果使用不同的 .NET Framework 版本序列化和反序列化以 UTF-8 或 UTF-7 编码的对象，则不保留该对象的状态。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-110">The state of a UTF-8 or UTF-7 encoded object is not preserved if the object is serialized and deserialized using different .NET Framework versions.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="e7bf6-111">二进制序列化允许修改对象内部的私有成员，从而更改其状态。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-111">Binary serialization allows modifying private members inside an object and therefore changing the state of it.</span></span> <span data-ttu-id="e7bf6-112">因此，建议在公共 API 图面上运行其他序列化框架，如 <xref:System.Text.Json?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-112">Because of this, other serialization frameworks, like <xref:System.Text.Json?displayProperty=fullName>, that operate on the public API surface are recommended.</span></span>

## <a name="net-core"></a><span data-ttu-id="e7bf6-113">.NET Core</span><span class="sxs-lookup"><span data-stu-id="e7bf6-113">.NET Core</span></span>

<span data-ttu-id="e7bf6-114">对于类型的子集，.NET Core 支持二进制序列化。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-114">.NET Core supports binary serialization for a subset of types.</span></span> <span data-ttu-id="e7bf6-115">可在后面的 "[可序列化类型](#serializable-types)" 部分中查看支持的类型列表。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-115">You can see the list of supported types in the [Serializable types](#serializable-types) section that follows.</span></span> <span data-ttu-id="e7bf6-116">在 .NET Framework 4.5.1 和更高版本之间以及 .NET Core 2.0 及更高版本之间，可以保证列出的类型是可序列化的。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-116">The listed types are guaranteed to be serializable between .NET Framework 4.5.1 and later versions and between .NET Core 2.0 and later versions.</span></span> <span data-ttu-id="e7bf6-117">其他 .NET 实现（如 Mono）不是正式支持的，但也应该有效。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-117">Other .NET implementations, such as Mono, aren't officially supported but should also work.</span></span>

### <a name="serializable-types"></a><span data-ttu-id="e7bf6-118">可序列化类型</span><span class="sxs-lookup"><span data-stu-id="e7bf6-118">Serializable types</span></span>

> [!div class="mx-tdCol2BreakAll"]
> | <span data-ttu-id="e7bf6-119">类型</span><span class="sxs-lookup"><span data-stu-id="e7bf6-119">Type</span></span> | <span data-ttu-id="e7bf6-120">注释</span><span class="sxs-lookup"><span data-stu-id="e7bf6-120">Notes</span></span> |
> | - | - |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-121">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-121">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-122">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-122">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AccessViolationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-123">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-123">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AggregateException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-124">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-124">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-125">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-125">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ApplicationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-126">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-126">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-127">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-127">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentNullException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-128">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-128">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-129">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-129">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArithmeticException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-130">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-130">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Array?displayProperty=nameWithType> | |
> | <xref:System.ArraySegment%601?displayProperty=nameWithType> | |
> | <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-131">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-131">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Attribute?displayProperty=nameWithType> | |
> | <xref:System.BadImageFormatException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-132">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-132">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Boolean?displayProperty=nameWithType> | |
> | <xref:System.Byte?displayProperty=nameWithType> | |
> | <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-133">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-133">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Char?displayProperty=nameWithType> | |
> | <xref:System.Collections.ArrayList?displayProperty=nameWithType> | |
> | <xref:System.Collections.BitArray?displayProperty=nameWithType> | |
> | <xref:System.Collections.Comparer?displayProperty=nameWithType> | |
> | <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-134">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-134">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Collections.Generic.KeyValuePair%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.LinkedList%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Stack%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Hashtable?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.Collection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Queue?displayProperty=nameWithType> | |
> | <xref:System.Collections.SortedList?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.HybridDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.ListDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringCollection?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Stack?displayProperty=nameWithType> | |
> | `System.Collections.Generic.NonRandomizedStringEqualityComparer` | <span data-ttu-id="e7bf6-135">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-135">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType> | |
> | <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-136">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-136">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-137">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-137">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-138">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-138">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-139">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-139">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-140">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-140">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="e7bf6-141">不支持从 .NET Framework 到 .NET Core 的序列化。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-141">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-142">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-142">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-143">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-143">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-144">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-144">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-145">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-145">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-146">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-146">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-147">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-147">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-148">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-148">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-149">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-149">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ContextMarshalException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-150">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-150">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DBNull?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-151">从 .NET Core 2.0.2 及更高版本开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-151">Starting in .NET Core 2.0.2 and later versions.</span></span> |
> | <xref:System.Data.Common.DbException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-152">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-152">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.ConstraintException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-153">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-153">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-154">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-154">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-155">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-155">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataSet?displayProperty=nameWithType> | |
> | <xref:System.Data.DataTable?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-156">如果将 `RemotingFormat` 设置为 `SerializationFormat.Binary`，则只能与 .NET Core 2.1 和更高版本交换。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-156">If you set `RemotingFormat` to `SerializationFormat.Binary`, it can only be exchanged with .NET Core 2.1 and later versions.</span></span> |
> | <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-157">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-157">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-158">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-158">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.EvaluateException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-159">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-159">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-160">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-160">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-161">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-161">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-162">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-162">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-163">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-163">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-164">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-164">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-165">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-165">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-166">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-166">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.PropertyCollection?displayProperty=nameWithType> | |
> | <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-167">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-167">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-168">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-168">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-169">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-169">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="e7bf6-170">不支持从 .NET Framework 到 .NET Core 的序列化</span><span class="sxs-lookup"><span data-stu-id="e7bf6-170">Serialization from .NET Framework to .NET Core is not supported</span></span> |
> | <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-171">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-171">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-172">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-172">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-173">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-173">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-174">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-174">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-175">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-175">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.StrongTypingException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-176">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-176">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-177">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-177">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-178">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-178">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DataMisalignedException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-179">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-179">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DateTime?displayProperty=nameWithType> | |
> | <xref:System.DateTimeOffset?displayProperty=nameWithType> | |
> | <xref:System.Decimal?displayProperty=nameWithType> | |
> | `System.Diagnostics.Contracts.ContractException` | <span data-ttu-id="e7bf6-180">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-180">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-181">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-181">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-182">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-182">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-183">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-183">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-184">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-184">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-185">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-185">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-186">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-186">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-187">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-187">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-188">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-188">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-189">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-189">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-190">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-190">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-191">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-191">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-192">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-192">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-193">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-193">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-194">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-194">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-195">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-195">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-196">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-196">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-197">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-197">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-198">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-198">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-199">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-199">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-200">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-200">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-201">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-201">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DivideByZeroException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-202">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-202">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DllNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-203">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-203">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Double?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Color?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Point?displayProperty=nameWithType> | |
> | <xref:System.Drawing.PointF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Rectangle?displayProperty=nameWithType> | |
> | <xref:System.Drawing.RectangleF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Size?displayProperty=nameWithType> | |
> | <xref:System.Drawing.SizeF?displayProperty=nameWithType> | |
> | <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-204">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-204">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-205">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-205">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Enum?displayProperty=nameWithType> | |
> | <xref:System.EventArgs?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-206">从 .NET Core 2.0.6 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-206">Starting in .NET Core 2.0.6.</span></span> |
> | <xref:System.Exception?displayProperty=nameWithType> | |
> | <xref:System.ExecutionEngineException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-207">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-207">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FieldAccessException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-208">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-208">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FormatException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-209">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-209">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> | |
> | <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-210">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-210">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.SortVersion?displayProperty=nameWithType> | |
> | <xref:System.Guid?displayProperty=nameWithType> | |
> | `System.IO.Compression.ZLibException` | <span data-ttu-id="e7bf6-211">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-211">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-212">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-212">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-213">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-213">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileFormatException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-214">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-214">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileLoadException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-215">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-215">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-216">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-216">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IOException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-217">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-217">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-218">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-218">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InvalidDataException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-219">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-219">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-220">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-220">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.PathTooLongException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-221">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-221">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-222">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-222">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-223">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-223">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientMemoryException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-224">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-224">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Int16?displayProperty=nameWithType> | |
> | <xref:System.Int32?displayProperty=nameWithType> | |
> | <xref:System.Int64?displayProperty=nameWithType> | |
> | <xref:System.IntPtr?displayProperty=nameWithType> | |
> | <xref:System.InvalidCastException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-225">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-225">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidOperationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-226">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-226">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidProgramException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-227">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-227">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-228">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-228">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MemberAccessException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-229">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-229">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MethodAccessException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-230">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-230">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingFieldException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-231">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-231">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMemberException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-232">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-232">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMethodException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-233">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-233">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-234">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-234">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Cookie?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieCollection?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieContainer?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-235">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-235">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.HttpListenerException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-236">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-236">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-237">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-237">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-238">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-238">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-239">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-239">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-240">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-240">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-241">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-241">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-242">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-242">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-243">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-243">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-244">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-244">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-245">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-245">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotFiniteNumberException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-246">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-246">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotImplementedException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-247">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-247">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-248">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-248">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NullReferenceException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-249">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-249">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Nullable%601?displayProperty=nameWithType> | |
> | <xref:System.Numerics.BigInteger?displayProperty=nameWithType> | |
> | <xref:System.Numerics.Complex?displayProperty=nameWithType> | |
> | <xref:System.Object?displayProperty=nameWithType> | |
> | <xref:System.ObjectDisposedException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-250">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-250">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OperationCanceledException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-251">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-251">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OutOfMemoryException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-252">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-252">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OverflowException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-253">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-253">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-254">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-254">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.RankException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-255">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-255">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-256">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-256">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-257">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-257">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-258">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-258">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-259">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-259">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="e7bf6-260">不支持从 .NET Framework 到 .NET Core 的序列化。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-260">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.Reflection.TargetException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-261">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-261">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-262">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-262">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-263">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-263">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-264">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-264">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-265">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-265">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-266">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-266">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-267">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-267">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-268">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-268">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-269">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-269">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-270">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-270">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-271">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-271">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-272">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-272">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-273">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-273">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-274">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-274">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-275">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-275">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-276">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-276">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.SByte?displayProperty=nameWithType> | |
> | <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-277">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-277">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-278">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-278">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-279">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-279">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-280">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-280">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-281">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-281">Starting in .NET Core 2.0.4.</span></span> |
> | `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` | <span data-ttu-id="e7bf6-282">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-282">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.HostProtectionException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-283">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-283">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-284">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-284">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-285">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-285">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.SecurityException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-286">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-286">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="e7bf6-287">限制的序列化数据。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-287">Limited serialization data.</span></span> |
> | <xref:System.Security.VerificationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-288">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-288">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-289">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-289">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-290">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-290">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Single?displayProperty=nameWithType> | |
> | <xref:System.StackOverflowException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-291">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-291">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.String?displayProperty=nameWithType> | |
> | <xref:System.StringComparer?displayProperty=nameWithType> | |
> | <xref:System.SystemException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-292">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-292">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-293">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-293">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-294">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-294">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-295">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-295">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.StringBuilder?displayProperty=nameWithType> | |
> | <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-296">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-296">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-297">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-297">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-298">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-298">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-299">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-299">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-300">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-300">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-301">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-301">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-302">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-302">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-303">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-303">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-304">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-304">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-305">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-305">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-306">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-306">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-307">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-307">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeSpan?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-308">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-308">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-309">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-309">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-310">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-310">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-311">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-311">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-312">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-312">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-313">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-313">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-314">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-314">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Tuple?displayProperty=nameWithType> | |
> | <xref:System.TypeAccessException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-315">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-315">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeInitializationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-316">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-316">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-317">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-317">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-318">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-318">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.UInt16?displayProperty=nameWithType> | |
> | <xref:System.UInt32?displayProperty=nameWithType> | |
> | <xref:System.UInt64?displayProperty=nameWithType> | |
> | <xref:System.UIntPtr?displayProperty=nameWithType> | |
> | <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-319">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-319">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Uri?displayProperty=nameWithType> | |
> | <xref:System.UriFormatException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-320">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-320">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ValueTuple?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-321">在 .NET Framework 4.7 及更早版本中不可序列化。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-321">Not serializable in .NET Framework 4.7 and earlier versions.</span></span> |
> | <xref:System.ValueType?displayProperty=nameWithType> | |
> | <xref:System.Version?displayProperty=nameWithType> | |
> | <xref:System.WeakReference%601?displayProperty=nameWithType> | |
> | <xref:System.WeakReference?displayProperty=nameWithType> | |
> | <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-322">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-322">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-323">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-323">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-324">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-324">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-325">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-325">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XmlException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-326">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-326">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-327">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-327">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> | <span data-ttu-id="e7bf6-328">从 .NET Core 2.0.4 开始。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-328">Starting in .NET Core 2.0.4.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e7bf6-329">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7bf6-329">See also</span></span>

- <xref:System.Runtime.Serialization>\
<span data-ttu-id="e7bf6-330">包含可用于序列化和反序列化对象的类。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-330">Contains classes that can be used for serializing and deserializing objects.</span></span>

- <span data-ttu-id="e7bf6-331">[XML 和 SOAP 序列化](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="e7bf6-331">[XML and SOAP Serialization](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span></span>\
<span data-ttu-id="e7bf6-332">描述随公共语言运行库一起提供的 XML 序列化机制。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-332">Describes the XML serialization mechanism that is included with the common language runtime.</span></span>

- <span data-ttu-id="e7bf6-333">[安全和序列化](../../../docs/framework/misc/security-and-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="e7bf6-333">[Security and Serialization](../../../docs/framework/misc/security-and-serialization.md)</span></span>\
<span data-ttu-id="e7bf6-334">描述写入执行序列化的代码时需要遵循的安全编码原则。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-334">Describes the secure coding guidelines to follow when writing code that performs serialization.</span></span>

- <span data-ttu-id="e7bf6-335">[.Net 远程处理](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e7bf6-335">[.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span></span>\
<span data-ttu-id="e7bf6-336">介绍 .NET Framework 中开始远程通信的各种方法。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-336">Describes the various methods Starting in .NET Framework for remote communications.</span></span>

- <span data-ttu-id="e7bf6-337">[使用 ASP.NET 和 Xml Web Services 客户端创建的 Xml Web Services](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e7bf6-337">[XML Web Services Created Using ASP.NET and XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>\
<span data-ttu-id="e7bf6-338">本文介绍和说明如何使用 ASP.NET 创建 XML Web services。</span><span class="sxs-lookup"><span data-stu-id="e7bf6-338">Articles that describe and explain how to program XML Web services created using ASP.NET.</span></span>
