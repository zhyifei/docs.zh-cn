---
title: "如何：映射 HRESULT 和异常 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "COM 互操作, 异常"
  - "COM 互操作, HRESULT"
  - "异常, HRESULT"
  - "HRESULT"
  - "与非托管代码间的互操作, 异常"
  - "与非托管代码间的互操作, HRESULT"
ms.assetid: 610b364b-2761-429d-9c4a-afbc3e66f1b9
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# 如何：映射 HRESULT 和异常
COM 方法通过返回 HRESULT 来报告错误；.NET 方法则通过引发异常来报告错误。  运行时将处理这两者之间的转换。  .NET Framework 中的每个异常类都会映射到一个 HRESULT。  
  
 用户定义的异常类可以指定任何适当的 HRESULT。  当通过设置异常对象的 **HResult** 字段来生成异常时，这些异常类可以动态地更改所返回的 HRESULT。  有关异常的其他信息通过 **IErrorInfo** 接口提供给客户端，该接口于非托管进程中在 .NET 对象上实现。  
  
 如果创建了扩展 **System.Exception** 的类，则必须在构造过程中设置 HRESULT 字段。  否则，基类将分配 HRESULT 值。  通过在异常的构造函数中提供 HRESULT 值，可以将新的异常类映射到现有的 HRESULT。  
  
 注意，当线程上存在 `IErrorInfo` 时，运行时有时会忽略 `HRESULT`。  该行为可能发生在 `HRESULT` 和 `IErrorInfo` 不表示相同错误的情况下。   ``  
  
### 新建异常类并将其映射到 HRESULT  
  
1.  使用以下代码新建一个名为 `NoAccessException` 的异常类并将它映射到 HRESULT `E_ACCESSDENIED`。  
  
    ```cpp  
    Class NoAccessException : public ApplicationException  
    {  
        NoAccessException () {  
        HResult = E_ACCESSDENIED;   
    }  
    }  
    CMyClass::MethodThatThrows  
    {  
    throw new NoAccessException();  
    }  
    ```  
  
 您可能遇到过同时使用托管和非托管代码的程序（以任何编程语言编写）。  例如，下面的代码示例中的自定义封送拆收器使用 **Marshal.ThrowExceptionForHR\(int HResult\)** 方法来引发具有特定 HRESULT 值的异常。  该方法将查找此 HRESULT 并生成相应的异常类型。  例如，下面的代码片段中的 HRESULT 将生成 **ArgumentException**。  
  
```cpp  
CMyClass::MethodThatThrows  
{  
    Marshal.ThrowExceptionForHR(COR_E_ARGUMENT);  
}  
```  
  
 下表提供了从每个 HRESULT 到它在 .NET Framework 中的可比异常类的完整关系映射。  
  
|HRESULT|.NET 异常|  
|-------------|-------------|  
|**MSEE\_E\_APPDOMAINUNLOADED**|**AppDomainUnloadedException**|  
|**COR\_E\_APPLICATION**|**ApplicationException**|  
|**COR\_E\_ARGUMENT 或 E\_INVALIDARG**|**ArgumentException**|  
|**COR\_E\_ARGUMENTOUTOFRANGE**|**ArgumentOutOfRangeException**|  
|**COR\_E\_ARITHMETIC 或 ERROR\_ARITHMETIC\_OVERFLOW**|**ArithmeticException**|  
|**COR\_E\_ARRAYTYPEMISMATCH**|**ArrayTypeMismatchException**|  
|**COR\_E\_BADIMAGEFORMAT 或 ERROR\_BAD\_FORMAT**|**BadImageFormatException**|  
|**COR\_E\_COMEMULATE\_ERROR**|**COMEmulateException**|  
|**COR\_E\_CONTEXTMARSHAL**|**ContextMarshalException**|  
|**COR\_E\_CORE**|**CoreException**|  
|**NTE\_FAIL**|**CryptographicException**|  
|**COR\_E\_DIRECTORYNOTFOUND 或 ERROR\_PATH\_NOT\_FOUND**|**DirectoryNotFoundException**|  
|**COR\_E\_DIVIDEBYZERO**|**DivideByZeroException**|  
|**COR\_E\_DUPLICATEWAITOBJECT**|**DuplicateWaitObjectException**|  
|**COR\_E\_ENDOFSTREAM**|**EndOfStreamException**|  
|**COR\_E\_TYPELOAD**|**EntryPointNotFoundException**|  
|**COR\_E\_EXCEPTION**|**异常**|  
|**COR\_E\_EXECUTIONENGINE**|**ExecutionEngineException**|  
|**COR\_E\_FIELDACCESS**|**FieldAccessException**|  
|**COR\_E\_FILENOTFOUND 或 ERROR\_FILE\_NOT\_FOUND**|**FileNotFoundException**|  
|**COR\_E\_FORMAT**|**FormatException**|  
|**COR\_E\_INDEXOUTOFRANGE**|**IndexOutOfRangeException**|  
|**COR\_E\_INVALIDCAST 或 E\_NOINTERFACE**|**InvalidCastException**|  
|**COR\_E\_INVALIDCOMOBJECT**|**InvalidComObjectException**|  
|**COR\_E\_INVALIDFILTERCRITERIA**|**InvalidFilterCriteriaException**|  
|**COR\_E\_INVALIDOLEVARIANTTYPE**|**InvalidOleVariantTypeException**|  
|**COR\_E\_INVALIDOPERATION**|**InvalidOperationException**|  
|**COR\_E\_IO**|**IOException**|  
|**COR\_E\_MEMBERACCESS**|**AccessException**|  
|**COR\_E\_METHODACCESS**|**MethodAccessException**|  
|**COR\_E\_MISSINGFIELD**|**MissingFieldException**|  
|**COR\_E\_MISSINGMANIFESTRESOURCE**|**MissingManifestResourceException**|  
|**COR\_E\_MISSINGMEMBER**|**MissingMemberException**|  
|**COR\_E\_MISSINGMETHOD**|**MissingMethodException**|  
|**COR\_E\_MULTICASTNOTSUPPORTED**|**MulticastNotSupportedException**|  
|**COR\_E\_NOTFINITENUMBER**|**NotFiniteNumberException**|  
|**E\_NOTIMPL**|**NotImplementedException**|  
|**COR\_E\_NOTSUPPORTED**|**NotSupportedException**|  
|**COR\_E\_NULLREFERENCE 或 E\_POINTER**|**NullReferenceException**|  
|**COR\_E\_OUTOFMEMORY 或**<br /><br /> **E\_OUTOFMEMORY**|**OutOfMemoryException**|  
|**COR\_E\_OVERFLOW**|**OverflowException**|  
|**COR\_E\_PATHTOOLONG 或 ERROR\_FILENAME\_EXCED\_RANGE**|**PathTooLongException**|  
|**COR\_E\_RANK**|**RankException**|  
|**COR\_E\_REFLECTIONTYPELOAD**|**ReflectionTypeLoadException**|  
|**COR\_E\_REMOTING**|**RemotingException**|  
|**COR\_E\_SAFEARRAYTYPEMISMATCH**|**SafeArrayTypeMismatchException**|  
|**COR\_E\_SECURITY**|**SecurityException**|  
|**COR\_E\_SERIALIZATION**|**SerializationException**|  
|**COR\_E\_STACKOVERFLOW 或 ERROR\_STACK\_OVERFLOW**|**StackOverflowException**|  
|**COR\_E\_SYNCHRONIZATIONLOCK**|**SynchronizationLockException**|  
|**COR\_E\_SYSTEM**|**SystemException**|  
|**COR\_E\_TARGET**|**TargetException**|  
|**COR\_E\_TARGETINVOCATION**|**TargetInvocationException**|  
|**COR\_E\_TARGETPARAMCOUNT**|**TargetParameterCountException**|  
|**COR\_E\_THREADABORTED**|**ThreadAbortException**|  
|**COR\_E\_THREADINTERRUPTED**|**ThreadInterruptedException**|  
|**COR\_E\_THREADSTATE**|**ThreadStateException**|  
|**COR\_E\_THREADSTOP**|**ThreadStopException**|  
|**COR\_E\_TYPELOAD**|**TypeLoadException**|  
|**COR\_E\_TYPEINITIALIZATION**|**TypeInitializationException**|  
|**COR\_E\_VERIFICATION**|**VerificationException**|  
|**COR\_E\_WEAKREFERENCE**|**WeakReferenceException**|  
|**COR\_E\_VTABLECALLSNOTSUPPORTED**|**VTableCallsNotSupportedException**|  
|**其他所有 HRESULT**|**COMException**|  
  
 要检索扩展的错误信息，托管客户端必须检查已生成的异常对象的字段。  要让异常对象提供有关错误的有用信息，COM 对象必须实现 **IErrorInfo** 接口。  运行时使用 **IErrorInfo** 所提供的信息来初始化异常对象。  
  
 如果 COM 对象不支持 **IErrorInfo**，运行时将用默认值初始化异常对象。  下表列出了与异常对象相关联的每个字段，并说明了当 COM 对象支持 **IErrorInfo** 时的默认信息源。  
  
 注意，当线程上存在 `IErrorInfo` 时，运行时有时会忽略 `HRESULT`。  该行为可能发生在 `HRESULT` 和 `IErrorInfo` 不表示相同错误的情况下。   ``  
  
|异常字段|COM 信息源|  
|----------|-------------|  
|**ErrorCode**|调用返回的 HRESULT。|  
|**HelpLink**|如果 **IErrorInfo\-\>HelpContext** 不为零，字符串将通过串联 **IErrorInfo\-\>GetHelpFile** 和“\#”和 **IErrorInfo\-\>GetHelpContext** 来形成。  否则，字符串将从 **IErrorInfo\-\>GetHelpFile** 返回。|  
|**InnerException**|始终为 null 引用（在 Visual Basic 中为 **Nothing**）。|  
|**消息**|**IErrorInfo\-\>GetDescription** 返回的字符串。|  
|**源**|**IErrorInfo\-\>GetSource** 返回的字符串。|  
|**StackTrace**|堆栈跟踪。|  
|**TargetSite**|返回失败 HRESULT 的方法的名称。|  
  
 **Message**、**Source** 和 **StackTrace** 等异常字段不可用于 **StackOverflowException**。  
  
## 请参阅  
 [Advanced COM Interoperability](http://msdn.microsoft.com/zh-cn/3ada36e5-2390-4d70-b490-6ad8de92f2fb)   
 [异常](../../../docs/standard/exceptions/index.md)