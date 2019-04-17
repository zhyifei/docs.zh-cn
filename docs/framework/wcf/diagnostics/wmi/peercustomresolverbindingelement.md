---
title: PeerCustomResolverBindingElement
ms.date: 03/30/2017
ms.assetid: 9ccc2770-a20e-4dff-9970-f56ad8aec2b5
ms.openlocfilehash: c7f8fd23133cd83ad87a00134b9755b94f531d8b
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613806"
---
# <a name="peercustomresolverbindingelement"></a>PeerCustomResolverBindingElement

PeerCustomResolverBindingElement

## <a name="syntax"></a>语法

```csharp
class PeerCustomResolverBindingElement : PeerResolverBindingElement
{
    string Address;
    string Binding;
};
```

## <a name="methods"></a>方法

PeerCustomResolverBindingElement 类不定义任何方法。

## <a name="properties"></a>属性

 PeerCustomResolverBindingElement 类具有下列属性：

### <a name="address"></a>Address

数据类型：String

访问类型：只读

对等自定义解析程序的地址。

### <a name="binding"></a>绑定

数据类型：String

访问类型：只读

绑定的配置名称。

## <a name="requirements"></a>要求

|MOF|已在 Servicemodel.mof 中声明。|
|---------|-----------------------------------|
|命名空间|已在 root\ServiceModel 中定义|

## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Channels.PeerCustomResolverBindingElement>
