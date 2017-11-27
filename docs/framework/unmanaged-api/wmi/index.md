---
title: "WMI 和性能计数器 （非托管 API 参考）"
description: "总结了.NET Framework WMI 和性能计数器信息的非托管 API。"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.date: 11/06/2017
ms.topic: article-type-from-white-list
ms.prod: .net-framework
ms.devlang: cpp
ms.openlocfilehash: 461d90aaf5beca1c0f1d1965ce0ea07411e56e79
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2017
---
# <a name="windows-management-instrumentation-wmi-and-performance-counters-unmanaged-api-reference"></a>Windows Management Instrumentation (WMI) 和性能计数器 （非托管 API 参考）

.NET Framework WMI 和性能计数器的非托管的 API 包含一组包装对的调用的函数[本机 Windows Management Instrumentation API](https://msdn.microsoft.com/library/aa389276(v=vs.85).aspx)。 它允许你开发工具和库的管理和监视远程计算机系统。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
该 API 包括以下功能：

| 函数 | 描述 |
|---------|---------|
| [BeginEnumeration 函数](beginenumeration.md) | 将枚举数重置到开头的 WMI 对象属性的枚举。 |
| [BeginMethodEnumeration 函数](beginmethodenumeration.md) |  开始为对象提供的方法的枚举。 |
| [BlessIWbemServices 函数](blessiwbemservices.md) | 指示用户凭据是否允许访问指定的 IWbemServices 类。 |
| [BlessIWbemServicesObject 函数](blessiwbemservicesobject.md) | 指示用户凭据是否允许与指定的 IWbem 服务对象的访问。 |
| [克隆函数](clone.md) | 返回是当前对象的完整克隆一个新对象。 |
| [CloneEnumWbemClassObject 函数](cloneenumwbemclassobject.md) | 生成的枚举，保留当前位置枚举中的逻辑副本。 |
| [CompareTo 函数](compareto.md) | 比较对象和另一个 Windows 管理对象。 |
| [ConnectServerWmi 函数](connectserverwmi.md) | 指定计算机上创建的 WMI 命名空间通过 DCOM 的连接。 |
| [CreateClassEnumWmi 函数](createclassenumwmi.md) | 返回满足指定的选择条件的所有类的枚举数。 |
| [CreateInstanceEnumWmi 函数](createinstanceenumwmi.md) | 返回一个枚举器返回满足指定的选择条件指定类的实例。 |
| [删除函数](delete.md) | 从类定义和所有其限定符中删除指定的属性。 |
| [Delete 方法函数](deletemethod.md) | 从 CIM 类定义中删除指定的方法。 |
| [EndEnumeration 函数](endenumeration.md) | 终止枚举序列。 | 
| [EndMethodEnumeration 函数](endmethodenumeration.md) | 终止通过调用启动枚举序列[BeginMethodEnumeration 函数](beginmethodenumeration.md)。 |
| [ExecNotificationQueryWmi 函数](execnotificationquerywmi.md) | 执行查询以接收事件。 |
| [ExecQueryWmi 函数](execquerywmi.md) | 执行查询以检索对象。 |
| [FormatFromRawValue 函数](formatfromrawvalue.md) | 基于时间的格式转换是否将转换为指定的格式中，一个原始性能数据值或两个原始性能数据值。 | 
| [Get 函数](get.md) | 如果它存在，请检索指定的属性值。 |
| [GetCurrentApartmentType 函数](getcurrentapartmenttype.md) | 检索在其中执行调用方的单元的类型。 |
| [GetDemultiplexedStub 函数](getdemultiplexedstub.md) | 创建的对象转发器接收器，以帮助客户端在从 Windows 管理接收异步调用。 |
| [GetErrorInfo 函数](geterrorinfo.md) | 从以前的函数调用中检索错误信息。 | 
| [GetMethod 函数](getmethod.md) | 检索有关指定方法的信息。 | 
| [GetMethodOrigin 函数](getmethodorigin.md) | 确定在其中声明了方法的类。 |
| [GetMethodQualifierSet 函数](getmethodqualifierset.md) | 检索为特定方法设置的限定符。 |
| [GetNames 函数](getnames.md) | 检索的子集或所有对象的属性的名称。 |
| [GetObjectText 函数](getobjecttext.md) | 用 MOF 语法返回对象的文本呈现。 | 
| [GetPropertyHandle 函数](getpropertyhandle.md) | 返回一个唯一的句柄，标识属性。 |
| [GetPropertyOrigin 函数](getpropertyorigin.md) | 确定所声明的属性的类。 |
| [GetPropertyQualifierSet 函数](getpropertyqualifierset.md) | 检索为特定的属性设置的限定符。  |
| [GetQualifierSet 函数](getqualifierset.md) | 检索为的类实例或类定义设置的限定符。 |
| [InheritsFrom 函数](inheritsfrom.md) | 确定当前类或实例派生自指定的父类别。 |
| [Initialize 函数](initialize.md) | 执行 WMI 初始化。 |
| [下一步函数](next.md) | 检索一个枚举中的下一步属性。 | 
| [NextMethod 函数](nextmethod.md) | 检索枚举中的下一步方法。 |
| [Put 的函数](put.md) | 将指定的属性设置为新值。 |
| [PutClassWmi 函数](putclasswmi.md) | 创建新的类或更新现有。 |
| [PutInstanceWmi 函数](putinstancewmi.md) | 创建或更新现有类的实例。 实例将写入 WMI 存储库。 |
| [PutMethod 函数](putmethod.md) | 创建一个方法。 |
| [QualifierSet_BeginEnumeration 函数](qualifierset-beginenumeration.md) | 将枚举数对象的限定符重置为枚举的开头。 |
| [QualifierSet_Delete 函数](qualifierset-delete.md) | 按名称删除指定的限定符。  |
| [QualifierSet_EndEnumeration 函数](qualifierset-endenumeration.md) | 终止通过调用开始枚举`QualifierSet_BeginEnumeration`函数。 |
| [QualifierSet_Get 函数](qualifierset-get.md) | 获取指定的命名的限定符。  |
| [QualifierSet_GetNames 函数](qualifierset-getnames.md) | 检索所有的限定符或指定限定符可从当前对象或属性的名称。 |
| [QualifierSet_Next 函数](qualifierset-next.md) | 检索一个枚举，通过调用启动中的下一步限定符[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)函数。 |
| [QualifierSet_Put 函数](qualifierset-put.md) | 写入命名的限定符和值。 |
| [ResetSecurity 函数](resetsecurity.md) | 将提供的模拟令牌分配给当前线程。 |
| [SetSecurity 函数](setsecurity.md) | 检索与当前线程关联的模拟令牌。 |
| [SpawnDerivedClass 函数](spawnderivedclass.md) | 从指定的对象创建新派生的类对象。 | 
| [SpawnInstance 函数](spawninstance.md) | 创建一个类的新实例。 |   
| [VerifyClient 函数](verifyclientkey.md) | 确保客户端密钥具有正确的安全性。 |
| [WritePropertyValue 函数](writepropertyvalue.md) | 将指定的数目的字节写入由属性句柄识别的属性。 |

 ## <a name="see-also"></a>请参阅
[非托管的 API 参考](../index.md) 