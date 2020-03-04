---
title: 如何编写用于 JSON 序列化的自定义转换器-.NET
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: 310967f39c3aa7a46d79087bcbf0cb016f7d7284
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159567"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a><span data-ttu-id="b85bb-102">如何编写 .NET 中的 JSON 序列化（封送处理）的自定义转换器</span><span class="sxs-lookup"><span data-stu-id="b85bb-102">How to write custom converters for JSON serialization (marshalling) in .NET</span></span>

<span data-ttu-id="b85bb-103">本文介绍如何为 <xref:[!OP.NO-LOC(System.Text.Json)]> 命名空间中提供的 JSON 序列化类创建自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="b85bb-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:[!OP.NO-LOC(System.Text.Json)]> namespace.</span></span> <span data-ttu-id="b85bb-104">有关 `[!OP.NO-LOC(System.Text.Json)]`的简介，请参阅[如何在 .net 中序列化和反序列化 JSON](system-text-json-how-to.md)。</span><span class="sxs-lookup"><span data-stu-id="b85bb-104">For an introduction to `[!OP.NO-LOC(System.Text.Json)]`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="b85bb-105">*转换器*是一个类，用于将对象或值转换为 JSON。</span><span class="sxs-lookup"><span data-stu-id="b85bb-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="b85bb-106">`[!OP.NO-LOC(System.Text.Json)]` 命名空间为映射到 JavaScript 基元的大多数基元类型提供内置的转换器。</span><span class="sxs-lookup"><span data-stu-id="b85bb-106">The `[!OP.NO-LOC(System.Text.Json)]` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="b85bb-107">可以编写自定义转换器：</span><span class="sxs-lookup"><span data-stu-id="b85bb-107">You can write custom converters:</span></span>

* <span data-ttu-id="b85bb-108">重写内置转换器的默认行为。</span><span class="sxs-lookup"><span data-stu-id="b85bb-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="b85bb-109">例如，你可能希望用 mm/dd/yyyy 格式而不是默认 ISO 8601-1:2019 格式来表示 `DateTime` 值。</span><span class="sxs-lookup"><span data-stu-id="b85bb-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="b85bb-110">支持自定义值类型。</span><span class="sxs-lookup"><span data-stu-id="b85bb-110">To support a custom value type.</span></span> <span data-ttu-id="b85bb-111">例如，`PhoneNumber` 结构。</span><span class="sxs-lookup"><span data-stu-id="b85bb-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="b85bb-112">你还可以编写自定义转换器，以自定义或扩展具有当前版本中未包含的功能的 `[!OP.NO-LOC(System.Text.Json)]`。</span><span class="sxs-lookup"><span data-stu-id="b85bb-112">You can also write custom converters to customize or extend `[!OP.NO-LOC(System.Text.Json)]` with functionality not included in the current release.</span></span> <span data-ttu-id="b85bb-113">本文的后面部分介绍了以下方案：</span><span class="sxs-lookup"><span data-stu-id="b85bb-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="b85bb-114">[将推理出的类型反序列化为对象属性](#deserialize-inferred-types-to-object-properties)。</span><span class="sxs-lookup"><span data-stu-id="b85bb-114">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="b85bb-115">[支持带有非字符串键的字典](#support-dictionary-with-non-string-key)。</span><span class="sxs-lookup"><span data-stu-id="b85bb-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="b85bb-116">[支持多态反序列化](#support-polymorphic-deserialization)。</span><span class="sxs-lookup"><span data-stu-id="b85bb-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="b85bb-117">自定义转换器模式</span><span class="sxs-lookup"><span data-stu-id="b85bb-117">Custom converter patterns</span></span>

<span data-ttu-id="b85bb-118">用于创建自定义转换器的模式有两种：基本模式和工厂模式。</span><span class="sxs-lookup"><span data-stu-id="b85bb-118">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="b85bb-119">工厂模式适用于处理类型 `Enum` 或开放式泛型的转换器。</span><span class="sxs-lookup"><span data-stu-id="b85bb-119">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="b85bb-120">基本模式适用于非泛型或封闭式泛型类型。</span><span class="sxs-lookup"><span data-stu-id="b85bb-120">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="b85bb-121">例如，以下类型的转换器需要工厂模式：</span><span class="sxs-lookup"><span data-stu-id="b85bb-121">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="b85bb-122">可以通过基本模式处理的类型的一些示例包括：</span><span class="sxs-lookup"><span data-stu-id="b85bb-122">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="b85bb-123">基本模式创建可处理一种类型的类。</span><span class="sxs-lookup"><span data-stu-id="b85bb-123">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="b85bb-124">工厂模式创建一个类，用于在运行时确定需要特定类型，并动态创建适当的转换器。</span><span class="sxs-lookup"><span data-stu-id="b85bb-124">The factory pattern creates a class that determines at runtime which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="b85bb-125">示例基本转换器</span><span class="sxs-lookup"><span data-stu-id="b85bb-125">Sample basic converter</span></span>

<span data-ttu-id="b85bb-126">下面的示例是一个转换器，用于重写现有数据类型的默认序列化。</span><span class="sxs-lookup"><span data-stu-id="b85bb-126">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="b85bb-127">转换器使用 mm/dd/yyyy 格式作为 `DateTimeOffset` 属性。</span><span class="sxs-lookup"><span data-stu-id="b85bb-127">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="b85bb-128">示例工厂模式转换器</span><span class="sxs-lookup"><span data-stu-id="b85bb-128">Sample factory pattern converter</span></span>

<span data-ttu-id="b85bb-129">下面的代码演示与 `Dictionary<Enum,TValue>`一起使用的自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="b85bb-129">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="b85bb-130">此代码遵循工厂模式，因为第一个泛型类型参数是 `Enum` 的，第二个是打开的。</span><span class="sxs-lookup"><span data-stu-id="b85bb-130">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="b85bb-131">`CanConvert` 方法仅对具有两个泛型参数的 `Dictionary` 返回 `true`，其中第一个参数是 `Enum` 类型。</span><span class="sxs-lookup"><span data-stu-id="b85bb-131">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="b85bb-132">内部转换器将获取一个现有转换器，用于处理在运行时为 `TValue`提供的任何类型。</span><span class="sxs-lookup"><span data-stu-id="b85bb-132">The inner converter gets an existing converter to handle whichever type is provided at runtime for `TValue`.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="b85bb-133">前面的代码与本文后面的[支持字典中包含非字符串密钥](#support-dictionary-with-non-string-key)的内容相同。</span><span class="sxs-lookup"><span data-stu-id="b85bb-133">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="b85bb-134">遵循基本模式的步骤</span><span class="sxs-lookup"><span data-stu-id="b85bb-134">Steps to follow the basic pattern</span></span>

<span data-ttu-id="b85bb-135">以下步骤说明了如何通过遵循基本模式创建转换器：</span><span class="sxs-lookup"><span data-stu-id="b85bb-135">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="b85bb-136">创建一个派生自 <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverter%601> 的类，其中 `T` 是要进行序列化和反序列化的类型。</span><span class="sxs-lookup"><span data-stu-id="b85bb-136">Create a class that derives from <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="b85bb-137">重写 `Read` 方法，以便反序列化传入 JSON 并将其转换为类型 `T`。</span><span class="sxs-lookup"><span data-stu-id="b85bb-137">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="b85bb-138">使用传递给方法的 <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonReader> 读取 JSON。</span><span class="sxs-lookup"><span data-stu-id="b85bb-138">Use the <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="b85bb-139">重写 `Write` 方法以序列化 `T`类型的传入对象。</span><span class="sxs-lookup"><span data-stu-id="b85bb-139">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="b85bb-140">使用传递给方法的 <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonWriter> 来写入 JSON。</span><span class="sxs-lookup"><span data-stu-id="b85bb-140">Use the <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="b85bb-141">仅在必要时重写 `CanConvert` 方法。</span><span class="sxs-lookup"><span data-stu-id="b85bb-141">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="b85bb-142">如果要转换的类型为类型 `T`，则默认实现将返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="b85bb-142">The default implementation returns `true` when the type to convert is of type `T`.</span></span> <span data-ttu-id="b85bb-143">因此，仅支持类型的转换器 `T` 不需要重写此方法。</span><span class="sxs-lookup"><span data-stu-id="b85bb-143">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="b85bb-144">有关的确需要重写此方法的转换器的示例，请参阅本文后面的多[态反序列化](#support-polymorphic-deserialization)部分。</span><span class="sxs-lookup"><span data-stu-id="b85bb-144">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="b85bb-145">可以参考[内置的转换器源代码](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/[!OP.NO-LOC(System.Text.Json)]/src/[!OP.NO-LOC(System/Text/Json)]/Serialization/Converters/)，作为编写自定义转换器的参考实现。</span><span class="sxs-lookup"><span data-stu-id="b85bb-145">You can refer to the [built-in converters source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/[!OP.NO-LOC(System.Text.Json)]/src/[!OP.NO-LOC(System/Text/Json)]/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="b85bb-146">遵循工厂模式的步骤</span><span class="sxs-lookup"><span data-stu-id="b85bb-146">Steps to follow the factory pattern</span></span>

<span data-ttu-id="b85bb-147">以下步骤说明了如何按照工厂模式创建转换器：</span><span class="sxs-lookup"><span data-stu-id="b85bb-147">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="b85bb-148">创建一个从 <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterFactory> 派生的类。</span><span class="sxs-lookup"><span data-stu-id="b85bb-148">Create a class that derives from <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="b85bb-149">重写 `CanConvert` 方法，以便在转换的类型是转换器可处理的类型时返回 true。</span><span class="sxs-lookup"><span data-stu-id="b85bb-149">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="b85bb-150">例如，如果转换器适用于 `List<T>` 则它可能仅处理 `List<int>`、`List<string>`和 `List<DateTime>`。</span><span class="sxs-lookup"><span data-stu-id="b85bb-150">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span>
* <span data-ttu-id="b85bb-151">重写 `CreateConverter` 方法，以返回将处理在运行时提供的类型转换的转换器类的实例。</span><span class="sxs-lookup"><span data-stu-id="b85bb-151">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at runtime.</span></span>
* <span data-ttu-id="b85bb-152">创建 `CreateConverter` 方法实例化的转换器类。</span><span class="sxs-lookup"><span data-stu-id="b85bb-152">Create the converter class that the `CreateConverter` method instantiates.</span></span>

<span data-ttu-id="b85bb-153">对于开放式泛型，必须使用工厂模式，因为用于将对象转换为字符串和从字符串转换的代码对于所有类型都是相同的。</span><span class="sxs-lookup"><span data-stu-id="b85bb-153">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="b85bb-154">例如，开放式泛型类型的转换器（例如`List<T>`）必须在幕后创建封闭式泛型类型（如`List<DateTime>`）的转换器。</span><span class="sxs-lookup"><span data-stu-id="b85bb-154">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="b85bb-155">必须编写代码来处理转换器可处理的每个封闭式泛型类型。</span><span class="sxs-lookup"><span data-stu-id="b85bb-155">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="b85bb-156">`Enum` 类型类似于开放式泛型类型： `Enum` 的转换器必须为特定的 `Enum` （例如`WeekdaysEnum`）创建转换器。</span><span class="sxs-lookup"><span data-stu-id="b85bb-156">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span>

## <a name="error-handling"></a><span data-ttu-id="b85bb-157">错误处理</span><span class="sxs-lookup"><span data-stu-id="b85bb-157">Error handling</span></span>

<span data-ttu-id="b85bb-158">如果需要在错误处理代码中引发异常，请考虑不使用消息引发 <xref:[!OP.NO-LOC(System.Text.Json)].JsonException>。</span><span class="sxs-lookup"><span data-stu-id="b85bb-158">If you need to throw an exception in error-handling code, consider throwing a <xref:[!OP.NO-LOC(System.Text.Json)].JsonException> without a message.</span></span> <span data-ttu-id="b85bb-159">此异常类型会自动创建一条消息，其中包括导致错误的 JSON 部分的路径。</span><span class="sxs-lookup"><span data-stu-id="b85bb-159">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="b85bb-160">例如，语句 `throw new JsonException();` 生成如下所示的错误消息：</span><span class="sxs-lookup"><span data-stu-id="b85bb-160">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```
Unhandled exception. [!OP.NO-LOC(System.Text.Json)].JsonException:
The JSON value could not be converted to System.Object.
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="b85bb-161">如果您提供了一条消息（例如 `throw new JsonException("Error occurred")`，则异常仍将在 <xref:[!OP.NO-LOC(System.Text.Json)].JsonException.Path> 属性中提供路径。</span><span class="sxs-lookup"><span data-stu-id="b85bb-161">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the exception still provides the path in the <xref:[!OP.NO-LOC(System.Text.Json)].JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="b85bb-162">注册自定义转换器</span><span class="sxs-lookup"><span data-stu-id="b85bb-162">Register a custom converter</span></span>

<span data-ttu-id="b85bb-163">*注册*自定义转换器，使 `Serialize` 和 `Deserialize` 方法使用它。</span><span class="sxs-lookup"><span data-stu-id="b85bb-163">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="b85bb-164">选择以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="b85bb-164">Choose one of the following approaches:</span></span>

* <span data-ttu-id="b85bb-165">向 <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters?displayProperty=nameWithType> 集合添加转换器类的实例。</span><span class="sxs-lookup"><span data-stu-id="b85bb-165">Add an instance of the converter class to the <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="b85bb-166">将[[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute)特性应用于需要自定义转换器的属性。</span><span class="sxs-lookup"><span data-stu-id="b85bb-166">Apply the [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="b85bb-167">将[[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute)特性应用于表示自定义值类型的类或结构。</span><span class="sxs-lookup"><span data-stu-id="b85bb-167">Apply the [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="b85bb-168">注册示例-转换器集合</span><span class="sxs-lookup"><span data-stu-id="b85bb-168">Registration sample - Converters collection</span></span>

<span data-ttu-id="b85bb-169">下面是一个示例，该示例将 <xref:System.ComponentModel.DateTimeOffsetConverter> 类型 <xref:System.DateTimeOffset>的属性的默认值：</span><span class="sxs-lookup"><span data-stu-id="b85bb-169">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

<span data-ttu-id="b85bb-170">假设您序列化以下类型的实例：</span><span class="sxs-lookup"><span data-stu-id="b85bb-170">Suppose you serialize an instance of the following type:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="b85bb-171">下面是显示使用自定义转换器的 JSON 输出示例：</span><span class="sxs-lookup"><span data-stu-id="b85bb-171">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="b85bb-172">下面的代码使用与使用自定义 `DateTimeOffset` 转换器相同的方法进行反序列化：</span><span class="sxs-lookup"><span data-stu-id="b85bb-172">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="b85bb-173">注册示例-属性上的 [JsonConverter]</span><span class="sxs-lookup"><span data-stu-id="b85bb-173">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="b85bb-174">下面的代码选择 `Date` 属性的自定义转换器：</span><span class="sxs-lookup"><span data-stu-id="b85bb-174">The following code selects a custom converter for the `Date` property:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

<span data-ttu-id="b85bb-175">序列化的代码 `WeatherForecastWithConverterAttribute` 不需要使用 `JsonSerializeOptions.Converters`：</span><span class="sxs-lookup"><span data-stu-id="b85bb-175">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

<span data-ttu-id="b85bb-176">要反序列化的代码也不需要使用 `Converters`：</span><span class="sxs-lookup"><span data-stu-id="b85bb-176">The code to deserialize also doesn't require the use of `Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="b85bb-177">注册示例-[JsonConverter] 类型</span><span class="sxs-lookup"><span data-stu-id="b85bb-177">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="b85bb-178">下面是创建结构并向其应用 `[JsonConverter]` 特性的代码：</span><span class="sxs-lookup"><span data-stu-id="b85bb-178">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Temperature.cs)]

<span data-ttu-id="b85bb-179">下面是前面的结构的自定义转换器：</span><span class="sxs-lookup"><span data-stu-id="b85bb-179">Here's the custom converter for the preceding struct:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/TemperatureConverter.cs)]

<span data-ttu-id="b85bb-180">结构上的 `[JsonConvert]` 特性将自定义转换器注册为 `Temperature`类型的属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="b85bb-180">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="b85bb-181">序列化或反序列化时，转换器会自动用于以下类型的 `TemperatureCelsius` 属性：</span><span class="sxs-lookup"><span data-stu-id="b85bb-181">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a><span data-ttu-id="b85bb-182">转换器注册优先顺序</span><span class="sxs-lookup"><span data-stu-id="b85bb-182">Converter registration precedence</span></span>

<span data-ttu-id="b85bb-183">在序列化或反序列化过程中，按以下顺序为每个 JSON 元素选择一个转换器，从最高优先级到最低优先级列出：</span><span class="sxs-lookup"><span data-stu-id="b85bb-183">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="b85bb-184">应用于属性的 `[JsonConverter]`。</span><span class="sxs-lookup"><span data-stu-id="b85bb-184">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="b85bb-185">添加到 `Converters` 集合中的转换器。</span><span class="sxs-lookup"><span data-stu-id="b85bb-185">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="b85bb-186">`[JsonConverter]` 应用于自定义值类型或 POCO。</span><span class="sxs-lookup"><span data-stu-id="b85bb-186">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="b85bb-187">如果在 `Converters` 集合中注册了某个类型的多个自定义转换器，则使用第一个为 `CanConvert` 返回 true 的转换器。</span><span class="sxs-lookup"><span data-stu-id="b85bb-187">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="b85bb-188">仅当未注册适用的自定义转换器时，才会选择内置转换器。</span><span class="sxs-lookup"><span data-stu-id="b85bb-188">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="b85bb-189">常见方案的转换器示例</span><span class="sxs-lookup"><span data-stu-id="b85bb-189">Converter samples for common scenarios</span></span>

<span data-ttu-id="b85bb-190">以下各节提供了一些转换器示例，用于解决内置功能不处理的一些常见方案。</span><span class="sxs-lookup"><span data-stu-id="b85bb-190">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

* [<span data-ttu-id="b85bb-191">反序列化推断类型到对象属性</span><span class="sxs-lookup"><span data-stu-id="b85bb-191">Deserialize inferred types to object properties</span></span>](#deserialize-inferred-types-to-object-properties)
* [<span data-ttu-id="b85bb-192">支持带有非字符串键的字典</span><span class="sxs-lookup"><span data-stu-id="b85bb-192">Support Dictionary with non-string key</span></span>](#support-dictionary-with-non-string-key)
* [<span data-ttu-id="b85bb-193">支持多态反序列化</span><span class="sxs-lookup"><span data-stu-id="b85bb-193">Support polymorphic deserialization</span></span>](#support-polymorphic-deserialization)

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="b85bb-194">反序列化推断类型到对象属性</span><span class="sxs-lookup"><span data-stu-id="b85bb-194">Deserialize inferred types to object properties</span></span>

<span data-ttu-id="b85bb-195">反序列化到类型 `object`的属性时，将创建一个 `JsonElement` 对象。</span><span class="sxs-lookup"><span data-stu-id="b85bb-195">When deserializing to a property of type `object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="b85bb-196">这是因为反序列化程序不知道要创建什么 CLR 类型，也不会尝试推测。</span><span class="sxs-lookup"><span data-stu-id="b85bb-196">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="b85bb-197">例如，如果 JSON 属性的值为 "true"，则反序列化程序不会推断值为 `Boolean`，如果元素有 "01/01/2019"，则反序列化程序不会推断出它是一个 `DateTime`。</span><span class="sxs-lookup"><span data-stu-id="b85bb-197">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="b85bb-198">类型推理可能不准确。</span><span class="sxs-lookup"><span data-stu-id="b85bb-198">Type inference can be inaccurate.</span></span> <span data-ttu-id="b85bb-199">如果反序列化程序分析的 JSON 数字没有小数点作为 `long`，则当最初将值序列化为 `ulong` 或 `BigInteger`时，这可能会导致超出范围的问题。</span><span class="sxs-lookup"><span data-stu-id="b85bb-199">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="b85bb-200">如果数字最初序列化为 `decimal`，则将带小数点的数字分析为 `double` 可能会损失精度。</span><span class="sxs-lookup"><span data-stu-id="b85bb-200">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="b85bb-201">对于需要类型推理的方案，以下代码演示了用于 `object` 属性的自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="b85bb-201">For scenarios that require type inference, the following code shows a custom converter for `object` properties.</span></span> <span data-ttu-id="b85bb-202">代码转换：</span><span class="sxs-lookup"><span data-stu-id="b85bb-202">The code converts:</span></span>

* <span data-ttu-id="b85bb-203">`true` 和 `false` `Boolean`</span><span class="sxs-lookup"><span data-stu-id="b85bb-203">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="b85bb-204">不带小数点的数字 `long`</span><span class="sxs-lookup"><span data-stu-id="b85bb-204">Numbers without a decimal to `long`</span></span>
* <span data-ttu-id="b85bb-205">带小数点的数字 `double`</span><span class="sxs-lookup"><span data-stu-id="b85bb-205">Numbers with a decimal to `double`</span></span>
* <span data-ttu-id="b85bb-206">要 `DateTime` 的日期</span><span class="sxs-lookup"><span data-stu-id="b85bb-206">Dates to `DateTime`</span></span>
* <span data-ttu-id="b85bb-207">要 `string` 的字符串</span><span class="sxs-lookup"><span data-stu-id="b85bb-207">Strings to `string`</span></span>
* <span data-ttu-id="b85bb-208">要 `JsonElement` 的其他内容</span><span class="sxs-lookup"><span data-stu-id="b85bb-208">Everything else to `JsonElement`</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

<span data-ttu-id="b85bb-209">下面的代码注册转换器：</span><span class="sxs-lookup"><span data-stu-id="b85bb-209">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeInferredTypesToObject.cs?name=SnippetRegister)]

<span data-ttu-id="b85bb-210">下面是包含 `object` 属性的示例类型：</span><span class="sxs-lookup"><span data-stu-id="b85bb-210">Here's an example type with `object` properties:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

<span data-ttu-id="b85bb-211">以下要反序列化的 JSON 示例包含将作为 `DateTime`、`long`和 `string`进行反序列化的值：</span><span class="sxs-lookup"><span data-stu-id="b85bb-211">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="b85bb-212">如果没有自定义转换器，反序列化会将 `JsonElement` 放入每个属性中。</span><span class="sxs-lookup"><span data-stu-id="b85bb-212">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="b85bb-213">`System.Text.Json.Serialization` 命名空间中的 "[单元测试" 文件夹](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/)包含用于处理反序列化到 `object` 属性的自定义转换器的更多示例。</span><span class="sxs-lookup"><span data-stu-id="b85bb-213">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to `object` properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="b85bb-214">支持带有非字符串键的字典</span><span class="sxs-lookup"><span data-stu-id="b85bb-214">Support Dictionary with non-string key</span></span>

<span data-ttu-id="b85bb-215">字典集合的内置支持适用于 `Dictionary<string, TValue>`。</span><span class="sxs-lookup"><span data-stu-id="b85bb-215">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="b85bb-216">也就是说，键必须是字符串。</span><span class="sxs-lookup"><span data-stu-id="b85bb-216">That is, the key must be a string.</span></span> <span data-ttu-id="b85bb-217">若要支持使用整数或其他类型作为键的字典，则需要自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="b85bb-217">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="b85bb-218">下面的代码演示适用于 `Dictionary<Enum,TValue>`的自定义转换器：</span><span class="sxs-lookup"><span data-stu-id="b85bb-218">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="b85bb-219">下面的代码注册转换器：</span><span class="sxs-lookup"><span data-stu-id="b85bb-219">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

<span data-ttu-id="b85bb-220">转换器可以序列化和反序列化以下类的 `TemperatureRanges` 属性，该类使用以下 `Enum`：</span><span class="sxs-lookup"><span data-stu-id="b85bb-220">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

<span data-ttu-id="b85bb-221">序列化的 JSON 输出类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="b85bb-221">The JSON output from serialization looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "Cold": 20,
    "Hot": 40
  }
}
```

<span data-ttu-id="b85bb-222">`System.Text.Json.Serialization` 命名空间中的 "[单元测试" 文件夹](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/)包含处理非字符串键字典的自定义转换器的更多示例。</span><span class="sxs-lookup"><span data-stu-id="b85bb-222">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="b85bb-223">支持多态反序列化</span><span class="sxs-lookup"><span data-stu-id="b85bb-223">Support polymorphic deserialization</span></span>

<span data-ttu-id="b85bb-224">内置功能提供有限范围的多[态序列化](system-text-json-how-to.md#serialize-properties-of-derived-classes)，但不支持反序列化。</span><span class="sxs-lookup"><span data-stu-id="b85bb-224">Built-in features provide a limited range of [polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) but no support for deserialization at all.</span></span> <span data-ttu-id="b85bb-225">反序列化需要自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="b85bb-225">Deserialization requires a custom converter.</span></span>

<span data-ttu-id="b85bb-226">例如，假设有一个 `Person` 抽象基类，其中包含 `Employee` 和 `Customer` 派生类。</span><span class="sxs-lookup"><span data-stu-id="b85bb-226">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="b85bb-227">多态反序列化意味着可以在设计时将 `Person` 指定为反序列化目标，并且 JSON 中的 `Customer` 和 `Employee` 对象在运行时正确地反序列化。</span><span class="sxs-lookup"><span data-stu-id="b85bb-227">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at runtime.</span></span> <span data-ttu-id="b85bb-228">在反序列化过程中，您必须查找识别 JSON 中所需类型的线索。</span><span class="sxs-lookup"><span data-stu-id="b85bb-228">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="b85bb-229">每个方案都有不同的可用线索类型。</span><span class="sxs-lookup"><span data-stu-id="b85bb-229">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="b85bb-230">例如，可以使用鉴别器属性，或者可能需要依赖于是否存在特定属性。</span><span class="sxs-lookup"><span data-stu-id="b85bb-230">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="b85bb-231">`System.Text.Json` 的当前版本不提供特性来指定如何处理多态反序列化方案，因此需要自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="b85bb-231">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="b85bb-232">下面的代码演示一个基类、两个派生类和一个基类的自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="b85bb-232">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="b85bb-233">转换器使用鉴别器属性执行多态反序列化。</span><span class="sxs-lookup"><span data-stu-id="b85bb-233">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="b85bb-234">类型鉴别器不在类定义中，而是在序列化过程中创建的，在反序列化期间读取。</span><span class="sxs-lookup"><span data-stu-id="b85bb-234">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

<span data-ttu-id="b85bb-235">下面的代码注册转换器：</span><span class="sxs-lookup"><span data-stu-id="b85bb-235">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPolymorphic.cs?name=SnippetRegister)]

<span data-ttu-id="b85bb-236">转换器可以反序列化使用同一转换器进行序列化而创建的 JSON，例如：</span><span class="sxs-lookup"><span data-stu-id="b85bb-236">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

```json
[
  {
    "TypeDiscriminator": 1,
    "CreditLimit": 10000,
    "Name": "John"
  },
  {
    "TypeDiscriminator": 2,
    "OfficeNumber": "555-1234",
    "Name": "Nancy"
  }
]
```

<span data-ttu-id="b85bb-237">前面的示例中的转换器代码将手动读取并写入每个属性。</span><span class="sxs-lookup"><span data-stu-id="b85bb-237">The converter code in the preceding example reads and writes each property manually.</span></span> <span data-ttu-id="b85bb-238">一种替代方法是调用 `Deserialize` 或 `Serialize` 来执行某些工作。</span><span class="sxs-lookup"><span data-stu-id="b85bb-238">An alternative is to call `Deserialize` or `Serialize` to do some of the work.</span></span> <span data-ttu-id="b85bb-239">有关示例，请参阅[此 StackOverflow 文章](https://stackoverflow.com/a/59744873/12509023)。</span><span class="sxs-lookup"><span data-stu-id="b85bb-239">For an example, see [this StackOverflow post](https://stackoverflow.com/a/59744873/12509023).</span></span>

## <a name="other-custom-converter-samples"></a><span data-ttu-id="b85bb-240">其他自定义转换器示例</span><span class="sxs-lookup"><span data-stu-id="b85bb-240">Other custom converter samples</span></span>

<span data-ttu-id="b85bb-241">[从 Newtonsoft.Json 迁移到 System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md)一文包含其他自定义转换器的示例。</span><span class="sxs-lookup"><span data-stu-id="b85bb-241">The [Migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) article contains additional samples of custom converters.</span></span>

<span data-ttu-id="b85bb-242">`System.Text.Json.Serialization` 源代码中的 "[单元测试" 文件夹](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/)包含其他自定义转换器示例，例如：</span><span class="sxs-lookup"><span data-stu-id="b85bb-242">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="b85bb-243">[在反序列化时将 null 转换为0的 Int32 转换器](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span><span class="sxs-lookup"><span data-stu-id="b85bb-243">[Int32 converter that converts null to 0 on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span></span>
* <span data-ttu-id="b85bb-244">[允许 string 和 number 值反序列化的 Int32 转换器](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span><span class="sxs-lookup"><span data-stu-id="b85bb-244">[Int32 converter that allows both string and number values on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span></span>
* <span data-ttu-id="b85bb-245">[枚举转换器](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span><span class="sxs-lookup"><span data-stu-id="b85bb-245">[Enum converter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span></span>
* <span data-ttu-id="b85bb-246">[列出接受外部数据\<T > 转换器](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span><span class="sxs-lookup"><span data-stu-id="b85bb-246">[List\<T> converter that accepts external data](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span></span>
* <span data-ttu-id="b85bb-247">[Long [] 转换器，适用于以逗号分隔的数字列表](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span><span class="sxs-lookup"><span data-stu-id="b85bb-247">[Long[] converter that works with a comma-delimited list of numbers](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span></span>

<span data-ttu-id="b85bb-248">如果需要创建一个修改现有内置转换器的行为的转换器，可以获取[现有转换器的源代码](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)，作为自定义的起点。</span><span class="sxs-lookup"><span data-stu-id="b85bb-248">If you need to make a converter that modifies the behavior of an existing built-in converter, you can get [the source code of the existing converter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) to serve as a starting point for customization.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b85bb-249">其他资源</span><span class="sxs-lookup"><span data-stu-id="b85bb-249">Additional resources</span></span>

* <span data-ttu-id="b85bb-250">[内置转换器的源代码](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span><span class="sxs-lookup"><span data-stu-id="b85bb-250">[Source code for built-in converters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span></span>
* <span data-ttu-id="b85bb-251">[System.Text.Json 中的 DateTime 和 DateTimeOffset 支持](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="b85bb-251">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="b85bb-252">[System.Text.Json 概述](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b85bb-252">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* <span data-ttu-id="b85bb-253">[如何使用 System.Text.Json](system-text-json-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="b85bb-253">[How to use System.Text.Json](system-text-json-how-to.md)</span></span>
* <span data-ttu-id="b85bb-254">[如何从 Newtonsoft.Json 迁移](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="b85bb-254">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* <span data-ttu-id="b85bb-255">[System.Text.Json API 参考](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="b85bb-255">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="b85bb-256">[System.Text.Json。序列化 API 参考](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="b85bb-256">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
