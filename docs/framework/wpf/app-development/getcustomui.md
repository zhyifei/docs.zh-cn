---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: e9ef32912c2afb3c99e46e1e14bb3daa5a2e99af
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005706"
---
# <a name="getcustomui"></a>GetCustomUI
由 Presentationhost.exe 调用，用于获取主机的自定义进度和错误消息（如果已实现）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a>Parameters  
 `pwzProgressAssemblyName`  
  
 弄指向包含主机提供的进度用户界面的程序集的指针。  
  
 `pwzProgressClassName`  
  
 弄类的名称，它是宿主提供的进度用户界面，最好是 @no__t 为-0 的 XAML 文件是其顶级元素。 此类驻留在由 `pwzProgressAssemblyName` 指定的程序集中。  
  
 `pwzErrorAssemblyName`  
  
 弄指向包含宿主提供的错误用户界面的程序集的指针。  
  
 `pwzErrorClassName`  
  
 弄类的名称，它是宿主提供的错误用户界面，最好是包含 <xref:System.Windows.Controls.Page> 的 XAML 文件是它的顶级元素。 此类驻留在由 `pwzErrorAssemblyName` 指定的程序集中。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 HRESULT：已忽略。  
  
## <a name="remarks"></a>备注  
 宿主应用程序可能有 Presentationhost.exe 的默认用户界面不符合的特定主题。 如果是这种情况，主机应用程序可以实现[GetCustomUI](getcustomui.md) ，将进度和错误用户界面返回到 presentationhost.exe。 Presentationhost.exe 在使用其默认用户界面之前，将始终调用[GetCustomUI](getcustomui.md) 。  
  
 此函数在 Presentationhost.exe 的初始化过程中调用一次。  
  
## <a name="see-also"></a>请参阅

- [IWpfHostSupport](iwpfhostsupport.md)
