---
title: CertTimestampAuthenticodeLicense 函数
ms.date: 03/30/2017
api_name:
- CertTimestampAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d468325a-21c5-43ce-8567-84e342b22308
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aaf76d4c3d0f5fb59aeb35fae7a7020ee97b74d6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776475"
---
# <a name="certtimestampauthenticodelicense-function"></a><span data-ttu-id="a35d6-102">CertTimestampAuthenticodeLicense 函数</span><span class="sxs-lookup"><span data-stu-id="a35d6-102">CertTimestampAuthenticodeLicense Function</span></span>
<span data-ttu-id="a35d6-103">为验证码 XrML 许可证添加时间戳。</span><span class="sxs-lookup"><span data-stu-id="a35d6-103">Time-stamps an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a35d6-104">语法</span><span class="sxs-lookup"><span data-stu-id="a35d6-104">Syntax</span></span>  
  
```cpp  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a35d6-105">参数</span><span class="sxs-lookup"><span data-stu-id="a35d6-105">Parameters</span></span>  
 `pSignedLicenseBlob`  
 <span data-ttu-id="a35d6-106">[in] 要添加时间戳的已签名验证码 XrML 许可证。</span><span class="sxs-lookup"><span data-stu-id="a35d6-106">[in] The signed Authenticode XrML license to be time-stamped.</span></span> <span data-ttu-id="a35d6-107">请参阅[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob)结构。</span><span class="sxs-lookup"><span data-stu-id="a35d6-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `pwszTimestampURI`  
 <span data-ttu-id="a35d6-108">[in] 时间戳服务器的 URI。</span><span class="sxs-lookup"><span data-stu-id="a35d6-108">[in] The time-stamp server's URI.</span></span>  
  
 `pTimestampSignatureBlob`  
 <span data-ttu-id="a35d6-109">[out] 指向 CRYPT_DATA_BLOB 的指针，用于接收 base64 编码的时间戳签名。</span><span class="sxs-lookup"><span data-stu-id="a35d6-109">[out] A pointer to CRYPT_DATA_BLOB to receive the base64-encoded time-stamp signature.</span></span> <span data-ttu-id="a35d6-110">调用方负责`pTimestampSignatureBlob` `HepFree()`在使用后释放->。 `pbData`</span><span class="sxs-lookup"><span data-stu-id="a35d6-110">It is the caller's responsibility to free `pTimestampSignatureBlob`->`pbData` with `HepFree()` after use.</span></span> <span data-ttu-id="a35d6-111">请参阅[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob)结构。</span><span class="sxs-lookup"><span data-stu-id="a35d6-111">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a35d6-112">备注</span><span class="sxs-lookup"><span data-stu-id="a35d6-112">Remarks</span></span>  
 <span data-ttu-id="a35d6-113">时间戳签名实际上是一条 PKCS #7 SignedData 消息，其内容是许可证签名中 SignatureValue 的二进制格式。</span><span class="sxs-lookup"><span data-stu-id="a35d6-113">The time-stamp signature is actually a PKCS #7 SignedData message whose content is the binary form of the SignatureValue from the license's signature.</span></span> <span data-ttu-id="a35d6-114">基本上，它充当许可证的副署。</span><span class="sxs-lookup"><span data-stu-id="a35d6-114">Basically, this acts as a counter-signature of the license.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a35d6-115">返回值</span><span class="sxs-lookup"><span data-stu-id="a35d6-115">Return Value</span></span>  
 <span data-ttu-id="a35d6-116">如果此函数成功，则返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="a35d6-116">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="a35d6-117">否则，返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="a35d6-117">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a35d6-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a35d6-118">See also</span></span>

- [<span data-ttu-id="a35d6-119">验证码</span><span class="sxs-lookup"><span data-stu-id="a35d6-119">Authenticode</span></span>](index.md)
