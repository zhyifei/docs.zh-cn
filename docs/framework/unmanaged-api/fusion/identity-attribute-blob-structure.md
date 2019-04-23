---
title: IDENTITY_ATTRIBUTE_BLOB 结构
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IDENTITY_ATTRIBUTE_BLOB
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE_BLOB
helpviewer_keywords:
- IDENTITY_ATTRIBUTE_BLOB structure [.NET Framework fusion]
ms.assetid: af14ae5f-d226-47dd-ba90-8fc6e6605d4d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 074cca51cee2b0227e1d124f1d40a2ffc31e3c85
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314069"
---
# <a name="identityattributeblob-structure"></a><span data-ttu-id="f6b0f-102">IDENTITY_ATTRIBUTE_BLOB 结构</span><span class="sxs-lookup"><span data-stu-id="f6b0f-102">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>
<span data-ttu-id="f6b0f-103">包含有关某个特性的程序集的信息，并由三个`DWORD`s。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-103">Contains information about a single attribute in an assembly, and consists of three `DWORD`s.</span></span> <span data-ttu-id="f6b0f-104">每个`DWORD`是由字符缓冲区偏移量`CurrentIntoBuffer`方法[IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)接口</span><span class="sxs-lookup"><span data-stu-id="f6b0f-104">Each `DWORD` is an offset into a character buffer produced by the `CurrentIntoBuffer` method of the [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) interface</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6b0f-105">语法</span><span class="sxs-lookup"><span data-stu-id="f6b0f-105">Syntax</span></span>  
  
```  
typedef struct _IDENTITY_ATTRIBUTE_BLOB {  
    DWORD  ofsNamespace;  
    DWORD  ofsName;  
    DWORD  ofsValue;  
}   IDENTITY_ATTRIBUTE_BLOB;  
```  
  
## <a name="members"></a><span data-ttu-id="f6b0f-106">成员</span><span class="sxs-lookup"><span data-stu-id="f6b0f-106">Members</span></span>  
  
|<span data-ttu-id="f6b0f-107">成员</span><span class="sxs-lookup"><span data-stu-id="f6b0f-107">Member</span></span>|<span data-ttu-id="f6b0f-108">描述</span><span class="sxs-lookup"><span data-stu-id="f6b0f-108">Description</span></span>|  
|------------|-----------------|  
|`ofsNamespace`|<span data-ttu-id="f6b0f-109">字符缓冲区中的第一个偏移量。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-109">The first offset into the character buffer.</span></span> <span data-ttu-id="f6b0f-110">未遵循此偏移量则由该特性的命名空间，而是一系列的 null 字符。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-110">This offset is not followed by the attribute's namespace, but by a series of null characters.</span></span> <span data-ttu-id="f6b0f-111">因此，不使用它。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-111">Therefore, it is not used.</span></span>|  
|`ofsName`|<span data-ttu-id="f6b0f-112">字符缓冲区中的第二个偏移量。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-112">The second offset into the character buffer.</span></span> <span data-ttu-id="f6b0f-113">此位置标记特性的名称的开头。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-113">This location marks the start of the attribute's name.</span></span>|  
|`ofsValue`|<span data-ttu-id="f6b0f-114">字符缓冲区中的第三个偏移量。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-114">The third offset into the character buffer.</span></span> <span data-ttu-id="f6b0f-115">此位置将标记属性的值的开头。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-115">This location marks the start of the attribute's value.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="f6b0f-116">示例</span><span class="sxs-lookup"><span data-stu-id="f6b0f-116">Sample</span></span>  
 <span data-ttu-id="f6b0f-117">下面的示例说明了几个基本步骤，最终会生成一个填充`IDENTITY_ATTRIBUTE_BLOB`结构：</span><span class="sxs-lookup"><span data-stu-id="f6b0f-117">The following example illustrates several basic steps, which eventually result in a populated `IDENTITY_ATTRIBUTE_BLOB` structure:</span></span>  
  
1. <span data-ttu-id="f6b0f-118">获取[IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)程序集。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-118">Obtain an [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) for the assembly.</span></span>  
  
2. <span data-ttu-id="f6b0f-119">调用`IReferenceIdentity::EnumAttributes`方法，并获取[IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-119">Call the `IReferenceIdentity::EnumAttributes` method, and obtain an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md).</span></span>  
  
3. <span data-ttu-id="f6b0f-120">创建字符缓冲区，并将其转换为`IDENTITY_ATTRIBUTE_BLOB`结构。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-120">Create a character buffer, and cast it as an `IDENTITY_ATTRIBUTE_BLOB` structure.</span></span>  
  
4. <span data-ttu-id="f6b0f-121">调用`CurrentIntoBuffer`方法的`IEnumIDENTITY_ATTRIBUTE`接口。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-121">Call the `CurrentIntoBuffer` method of the `IEnumIDENTITY_ATTRIBUTE` interface.</span></span> <span data-ttu-id="f6b0f-122">此方法将这些属性复制`Namespace`， `Name`，和`Value`字符缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-122">This method copies the attributes `Namespace`, `Name`, and `Value` into the character buffer.</span></span> <span data-ttu-id="f6b0f-123">为这些字符串的三个偏移量将变为可用在`IDENTITY_ATTRIBUTE_BLOB`结构。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-123">The three offsets to those strings will become available in the `IDENTITY_ATTRIBUTE_BLOB` structure.</span></span>  
  
```  
// EnumAssemblyAttributes.cpp : main project file.  
  
#include "stdafx.h"  
  
#include "fusion.h"  
#include "windows.h"  
#include "stdio.h"  
#include "mscoree.h"  
#include "isolation.h"  
  
typedef HRESULT (__stdcall *PFNGETREF)(LPCWSTR pwzFile, REFIID riid, IUnknown **ppUnk);  
typedef HRESULT (__stdcall *PFNGETAUTH)(IIdentityAuthority **ppIIdentityAuthority);  
  
PFNGETREF                   g_pfnGetAssemblyIdentityFromFile = NULL;  
PFNGETAUTH                  g_pfnGetIdentityAuthority = NULL;  
IUnknown                    *g_pUnk = NULL;  
  
bool Init()  
{  
    HRESULT     hr = S_OK;  
    DWORD       dwSize = 0;  
    bool        bRC = false;  
  
    hr = CorBindToRuntimeEx(NULL, L"wks", 0, CLSID_CorRuntimeHost,  
                           IID_ICorRuntimeHost, (void **)&g_pUnk);  
    if(FAILED(hr)) {  
        printf("Error: Failed to initialize CLR runtime! hr = 0x%0x\n",  
                hr);  
        goto Exit;  
    }  
  
    if (SUCCEEDED(hr)) {  
        hr = GetRealProcAddress("GetAssemblyIdentityFromFile",  
                         (VOID **)&g_pfnGetAssemblyIdentityFromFile);  
    }  
  
    if (SUCCEEDED(hr)) {  
        hr = GetRealProcAddress("GetIdentityAuthority",  
                                (VOID **)&g_pfnGetIdentityAuthority);  
    }  
  
    if (!g_pfnGetAssemblyIdentityFromFile ||   
        !g_pfnGetIdentityAuthority)  
    {  
        printf("Error: Cannot get required APIs from fusion.dll!\n");  
        goto Exit;  
    }  
  
    bRC = true;  
  
Exit:  
    return bRC;  
}  
  
void Shutdown()  
{  
    if(g_pUnk) {  
        g_pUnk->Release();  
        g_pUnk = NULL;  
    }  
}  
  
void Usage()  
{  
    printf("EnumAssemblyAttributes: A tool to enumerate the identity   
            attributes of a given assembly.\n\n");  
    printf("Usage: EnumAssemblyAttributes AssemblyFilePath\n");  
    printf("\n");  
}  
  
int _cdecl wmain(int argc, LPCWSTR argv[])  
{  
    int     iResult = 1;  
    IUnknown                    *pUnk  = NULL;  
    IReferenceIdentity          *pRef  = NULL;  
    HRESULT                     hr     = S_OK;     
    IEnumIDENTITY_ATTRIBUTE     *pEnum = NULL;  
    BYTE                        abData[1024];  
    DWORD                       cbAvailable;  
    DWORD                       cbUsed;  
    IDENTITY_ATTRIBUTE_BLOB     *pBlob;  
  
    if(argc != 2) {  
        Usage();  
        goto Exit;  
    }  
  
    if(!Init()) {  
        printf("Failure initializing EnumIdAttr.\n");  
        goto Exit;  
    }  
  
    hr = g_pfnGetAssemblyIdentityFromFile(argv[1],   
                            __uuidof(IReferenceIdentity), &pUnk);  
  
    if (FAILED(hr)) {  
        printf("GetAssemblyIdentityFromFile failed with hr = 0x%x",   
                hr);  
        goto Exit;  
    }  
  
    hr = pUnk->QueryInterface(__uuidof(IReferenceIdentity),   
                              (void**)&pRef);  
    if (FAILED(hr)) {  
        goto Exit;  
    }  
  
    hr = pRef->EnumAttributes(&pEnum);  
    if (FAILED(hr)) {  
        printf("IReferenceIdentity::EnumAttributes failed with hr =   
                0x%x", hr);  
        goto Exit;  
    }  
  
    pBlob = (IDENTITY_ATTRIBUTE_BLOB *)(abData);  
    while (1) {  
        cbAvailable = sizeof(abData);  
        hr = pEnum->CurrentIntoBuffer(cbAvailable, abData, &cbUsed);  
        if (FAILED(hr)) {  
            printf("IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer failed   
                    with hr = 0x%x", hr);  
            goto Exit;  
        }  
  
        if (! cbUsed) {  
            break;  
        }  
  
        LPWSTR pwzNameSpace = (LPWSTR)(abData + pBlob->ofsNamespace);  
        LPWSTR pwzName      = (LPWSTR)(abData + pBlob->ofsName);  
        LPWSTR pwzValue     = (LPWSTR)(abData + pBlob->ofsValue);  
        printf("%ws: %ws = %ws\n", pwzNameSpace, pwzName, pwzValue);  
  
        hr = pEnum->Skip(1);  
        if (FAILED(hr)) {  
            printf("IEnumIDENTITY_ATTRIBUTE::Skip failed with hr =   
                    0x%x", hr);  
            goto Exit;  
        }  
    }  
  
    iResult = 0;  
  
Exit:  
  
    Shutdown();  
  
    if (pUnk) {  
        pUnk->Release();  
    }  
  
    if (pRef) {  
        pRef->Release();  
    }  
  
    if (pEnum) {  
        pEnum->Release();  
    }  
  
    return iResult;  
}  
```  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="f6b0f-124">运行示例</span><span class="sxs-lookup"><span data-stu-id="f6b0f-124">To run the sample</span></span>  
 <span data-ttu-id="f6b0f-125">C:\\> EnumAssemblyAttributes.exe C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\System.dll</span><span class="sxs-lookup"><span data-stu-id="f6b0f-125">C:\\> EnumAssemblyAttributes.exe C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\System.dll</span></span>  
  
### <a name="sample-output"></a><span data-ttu-id="f6b0f-126">示例输出</span><span class="sxs-lookup"><span data-stu-id="f6b0f-126">Sample output</span></span>  
 <span data-ttu-id="f6b0f-127">区域性 = 中性</span><span class="sxs-lookup"><span data-stu-id="f6b0f-127">Culture = neutral</span></span>  
  
 <span data-ttu-id="f6b0f-128">名称 = 系统</span><span class="sxs-lookup"><span data-stu-id="f6b0f-128">name = System</span></span>  
  
 <span data-ttu-id="f6b0f-129">processorArchitecture = MSIL</span><span class="sxs-lookup"><span data-stu-id="f6b0f-129">processorArchitecture = MSIL</span></span>  
  
 <span data-ttu-id="f6b0f-130">PublicKeyToken = b77a5c561934e089</span><span class="sxs-lookup"><span data-stu-id="f6b0f-130">PublicKeyToken = b77a5c561934e089</span></span>  
  
 <span data-ttu-id="f6b0f-131">版本 = 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="f6b0f-131">Version = 2.0.0.0</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6b0f-132">要求</span><span class="sxs-lookup"><span data-stu-id="f6b0f-132">Requirements</span></span>  
 <span data-ttu-id="f6b0f-133">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6b0f-134">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="f6b0f-134">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="f6b0f-135">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6b0f-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6b0f-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6b0f-136">See also</span></span>

- [<span data-ttu-id="f6b0f-137">IReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="f6b0f-137">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
- [<span data-ttu-id="f6b0f-138">IEnumIDENTITY_ATTRIBUTE 接口</span><span class="sxs-lookup"><span data-stu-id="f6b0f-138">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
- [<span data-ttu-id="f6b0f-139">IDENTITY_ATTRIBUTE 结构</span><span class="sxs-lookup"><span data-stu-id="f6b0f-139">IDENTITY_ATTRIBUTE Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-structure.md)
- [<span data-ttu-id="f6b0f-140">合成结构</span><span class="sxs-lookup"><span data-stu-id="f6b0f-140">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
