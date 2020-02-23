---
ms.openlocfilehash: 8d3a8712528d2d35c706cc26b8c388b65d6ad506
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449203"
---
### <a name="better-argument-validation-in-the-pkcs8privatekeyinfo-constructor"></a><span data-ttu-id="8c9f8-101">Pkcs8PrivateKeyInfo 构造函数中更好的参数验证</span><span class="sxs-lookup"><span data-stu-id="8c9f8-101">Better argument validation in the Pkcs8PrivateKeyInfo constructor</span></span>

<span data-ttu-id="8c9f8-102">从 .NET Core 3.0 预览版 9 开始，`Pkcs8PrivateKeyInfo` 构造函数将 `algorithmParameters` 参数作为单一 BER 编码值进行验证。</span><span class="sxs-lookup"><span data-stu-id="8c9f8-102">Starting with .NET Core 3.0 Preview 9, the `Pkcs8PrivateKeyInfo` constructor validates the `algorithmParameters` parameter as a single BER-encoded value.</span></span>

#### <a name="change-description"></a><span data-ttu-id="8c9f8-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="8c9f8-103">Change description</span></span>

<span data-ttu-id="8c9f8-104">在 .NET Core 3.0 预览版 9 之前，[`Pkcs8PrivateKeyInfo` 构造函数](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean))不验证 `algorithmParameters` 参数。</span><span class="sxs-lookup"><span data-stu-id="8c9f8-104">Before .NET Core 3.0 Preview 9, the [`Pkcs8PrivateKeyInfo` constructor](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean)) did not validate the `algorithmParameters` argument.</span></span>  <span data-ttu-id="8c9f8-105">如果此参数表示的值无效，构造函数仍会成功，但对任何 <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode>、<xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncode%2A>、<xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encrypt%2A> 或 <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncrypt%2A> 方法的调用将引发 <xref:System.ArgumentException>（对于其不接受的参数）(`preEncodedValue`) 或 <xref:System.Security.Cryptography.CryptographicException>。</span><span class="sxs-lookup"><span data-stu-id="8c9f8-105">When this argument represented an invalid value, the constructor would succeed, but a call to any of the <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncode%2A>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encrypt%2A>, or <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncrypt%2A> methods would throw either an <xref:System.ArgumentException> for an argument they did not accept (`preEncodedValue`) or a <xref:System.Security.Cryptography.CryptographicException>.</span></span>

<span data-ttu-id="8c9f8-106">如果运行 .NET Core 3.0 预览版 9 之前的版本，则以下代码仅在调用 <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode> 方法时引发异常：</span><span class="sxs-lookup"><span data-stu-id="8c9f8-106">If run with .NET Core 3.0 before Preview 9, the following code throws an exception only when the <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode> method is called:</span></span>

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
// This line throws an ArgumentException for `preEncodedValue`:
byte[] encoded = info.Encode();
```

<span data-ttu-id="8c9f8-107">从 .NET Core 3.0 预览版 9 开始，参数在构造函数中进行验证，无效值导致方法引发 <xref:System.Security.Cryptography.CryptographicException>。</span><span class="sxs-lookup"><span data-stu-id="8c9f8-107">Starting with .NET Core 3.0 Preview 9, the argument is validated in the constructor, and an invalid value results in the method throwing a <xref:System.Security.Cryptography.CryptographicException>.</span></span> <span data-ttu-id="8c9f8-108">此更改使异常更接近数据错误源。</span><span class="sxs-lookup"><span data-stu-id="8c9f8-108">This change moves the exception closer to the source of the data error.</span></span> <span data-ttu-id="8c9f8-109">例如：</span><span class="sxs-lookup"><span data-stu-id="8c9f8-109">For example:</span></span>

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

// This line throws a CryptographicException
var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
```

#### <a name="version-introduced"></a><span data-ttu-id="8c9f8-110">引入的版本</span><span class="sxs-lookup"><span data-stu-id="8c9f8-110">Version introduced</span></span>

<span data-ttu-id="8c9f8-111">3.0 预览版 9</span><span class="sxs-lookup"><span data-stu-id="8c9f8-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8c9f8-112">建议操作</span><span class="sxs-lookup"><span data-stu-id="8c9f8-112">Recommended action</span></span>

<span data-ttu-id="8c9f8-113">请确保只提供有效的 `algorithmParameters` 值，否则对 `Pkcs8PrivateKeyInfo` 构造函数的调用既测试 <xref:System.ArgumentException> 也测试 <xref:System.Security.Cryptography.CryptographicException>（如果需要异常处理）。</span><span class="sxs-lookup"><span data-stu-id="8c9f8-113">Ensure that only valid `algorithmParameters` values are provided, or that calls to the `Pkcs8PrivateKeyInfo` constructor test for both <xref:System.ArgumentException> and <xref:System.Security.Cryptography.CryptographicException> if exception handling is desired.</span></span>

### <a name="category"></a><span data-ttu-id="8c9f8-114">类别</span><span class="sxs-lookup"><span data-stu-id="8c9f8-114">Category</span></span>

<span data-ttu-id="8c9f8-115">密码</span><span class="sxs-lookup"><span data-stu-id="8c9f8-115">Cryptography</span></span>

### <a name="affected-apis"></a><span data-ttu-id="8c9f8-116">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="8c9f8-116">Affected APIs</span></span>

- <span data-ttu-id="8c9f8-117">[Pkcs8PrivateKeyInfo 构造函数](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean))</span><span class="sxs-lookup"><span data-stu-id="8c9f8-117">[Pkcs8PrivateKeyInfo constructor](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean))</span></span>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.#ctor(System.Security.Cryptography.Oid,System.Nullable{System.ReadOnlyMemory{System.Byte}},System.ReadOnlyMemory{System.Byte},System.Boolean)`

-->
