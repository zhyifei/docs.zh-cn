---
title: "数组的默认封送处理 | Microsoft Docs"
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
  - "数组, 互操作封送处理"
  - "互操作封送处理, 数组"
ms.assetid: 8a3cca8b-dd94-4e3d-ad9a-9ee7590654bc
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# 数组的默认封送处理
在完全由托管代码组成的应用程序中，公共语言运行时将数组类型作为 In\/Out 参数传递。  与此相对，Interop 封送拆收器在默认情况下将数组作为 In 参数传递。  
  
 使用[锁定优化](../../../docs/framework/interop/copying-and-pinning.md)，可直接复制到本机结构中的数组在与同一单元中的对象交互时可能看上去像是作为 In\/Out 参数在运行。  但是，如果随后将代码导出到用于生成跨计算机代理的类型库，而该库被用于封送跨单元的调用，则调用可以还原为真实的 In 参数行为。  
  
 数组本质上是复杂的，而托管和非托管数组之间的差异则意味着需要了解比其他非直接复制到本机结构中的类型更多的信息。  本主题提供下列有关封送数组的信息：  
  
-   [托管数组](#cpcondefaultmarshalingforarraysanchor1)  
  
-   [非托管数组](#cpcondefaultmarshalingforarraysanchor2)  
  
-   [将数组参数传递给 .NET 代码](#cpcondefaultmarshalingforarraysanchor3)  
  
-   [将数组传递给 COM](#cpcondefaultmarshalingforarraysanchor4)  
  
<a name="cpcondefaultmarshalingforarraysanchor1"></a>   
## 托管数组  
 托管数组类型可以是各种各样的；但是，<xref:System.Array?displayProperty=fullName> 类是所有数组类型的基类。  **System.Array** 类具有用于确定数组的秩、长度、下限和上限的属性，还有用于对数组进行访问、排序、搜索、复制和创建的方法。  
  
 这些数组类型是动态的，而且在基类库中没有相应的已定义的静态类型。  将元素类型和秩的每种组合视为不同类型的数组非常方便。  因此，一维整数数组与一维双精度类型数组是不同的类型。  与此类似，二维整数数组也与一维整数数组不同。  比较类型时不考虑数组的界限。  
  
 如下表所示，托管数组的任何实例都必须有特定的元素类型、秩和下限。  
  
|托管数组类型|元素类型|级别|下限|签名表示法|  
|------------|----------|--------|--------|-----------|  
|**ELEMENT\_TYPE\_ARRAY**|由类型指定。|由秩指定。|可随意地由界限指定。|*type* **\[** *n*,*m* **\]**|  
|**ELEMENT\_TYPE\_CLASS**|未知|未知|未知|**System.Array**|  
|**ELEMENT\_TYPE\_SZARRAY**|由类型指定。|1|0|*type* **\[** *n* **\]**|  
  
<a name="cpcondefaultmarshalingforarraysanchor2"></a>   
## 非托管数组  
 非托管数组是具有固定或可变长度的 COM 样式安全数组或 C 样式数组。  安全数组是具有与之关联的数组数据的类型、秩和界限的自我描述数组。  C 样式数组是具有固定下限 0 的一维类型化数组。  封送处理服务有限地支持这两种类型的数组。  
  
<a name="cpcondefaultmarshalingforarraysanchor3"></a>   
## 将数组参数传递给 .NET 代码  
 C 样式数组和安全数组都可以作为安全数组或 C 样式数组从非托管代码传递给 .NET 代码。  下表显示非托管类型值和导入的类型。  
  
|非托管类型|导入的类型|  
|-----------|-----------|  
|**SafeArray\(** *Type* **\)**|**ELEMENT\_TYPE\_SZARRAY** **\<** *ConvertedType* **\>**<br /><br /> 秩 \= 1，下限 \= 0。  只有在托管签名中提供大小时，大小才是已知的。  不满足秩 \= 1 或下限 \= 0 的安全数组不能作为 **SZARRAY** 封送。|  
|*Type*  **\[\]**|**ELEMENT\_TYPE\_SZARRAY** **\<** *ConvertedType* **\>**<br /><br /> 秩 \= 1，下限 \= 0。  只有在托管签名中提供大小时，大小才是已知的。|  
  
### 安全数组  
 当从类型库中将安全数组导入 .NET 程序集中时，该数组将被转换为已知类型（如 **int**）的一维数组。  适用于参数的同样的类型转换规则也适用于数组元素。  例如，**BSTR** 类型的安全数组可变为托管字符串数组，而变量的安全数组可变为托管对象数组。  **SAFEARRAY** 元素类型从类型库中捕获并保存在 <xref:System.Runtime.InteropServices.UnmanagedType> 枚举的 **SAFEARRAY** 值中。  
  
 由于安全数组的秩和界限不能根据类型库确定，因此假定秩等于 1，而假定下限等于 0。  秩和界限必须在由[类型库导入程序 \(Tlbimp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) 产生的托管签名中定义。  如果运行时传递给方法的秩不同，则将引发 <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException>。  如果运行时传递的数组的类型不同，则将引发 <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException>。  下面的示例显示托管代码和非托管代码中的安全数组。  
  
 **非托管签名**  
  
```  
HRESULT New1([in] SAFEARRAY( int ) ar);  
HRESULT New2([in] SAFEARRAY( DATE ) ar);  
HRESULT New3([in, out] SAFEARRAY( BSTR ) *ar);  
```  
  
 **托管签名**  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_I4)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_DATE)> _   
   ar() As DateTime)  
Sub New3(ByRef <MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_BSTR)> _   
   ar() As String)  
  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_I4)] int[] ar) ;  
void New2([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_DATE)]   
   DateTime[] ar);  
void New3([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_BSTR)]   
   ref String[] ar);  
```  
  
 如果修改由 Tlbimp.exe 产生的方法签名以指示元素类型 **ELEMENT\_TYPE\_ARRAY** 而不是元素类型 **ELEMENT\_TYPE\_SZARRAY**，则可以将多维或不以零为界限的安全数组封送到托管代码中。  或者，可以将 **\/sysarray** 开关与 Tlbimp.exe 一起使用，以将所有数组作为 <xref:System.Array?displayProperty=fullName> 对象导入。  如果已知正在传递的数组是多维数组，则可以编辑由 Tlbimp.exe 产生的 Microsoft 中间语言 \(MSIL\) 代码，然后重新编译它。  有关如何修改 MSIL 代码的详细信息，请参见[自定义运行时可调用包装](http://msdn.microsoft.com/zh-cn/4652beaf-77d0-4f37-9687-ca193288c0be)。  
  
### C 样式数组  
 在将 C 样式数组从类型库导入 .NET 程序集中时，数组被转换为 **ELEMENT\_TYPE\_SZARRAY**。  
  
 数组元素类型根据类型库确定并在导入期间保留。  适用于参数的同样的转换规则也适用于数组元素。  例如，**LPStr** 类型的数组变为 **String** 类型的数组。  Tlbimp.exe 捕获数组元素类型并将 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 特性应用于该参数。  
  
 假定数组秩等于 1。  如果秩大于 1，则将以列优先的顺序将数组作为一维数组封送。  下限始终等于 0。  
  
 类型库可以包含固定或可变长度的数组。  Tlbimp.exe 只能从类型库中导入定长的数组，这是因为类型库缺少封送可变长度数组所需的信息。  对于定长的数组，大小从类型库中导入并在应用于参数的 **MarshalAsAttribute** 中捕获。  
  
 必须手动定义包含可变长度数组的类型库，如下面的示例中所示。  
  
 **非托管签名**  
  
```  
HRESULT New1(int ar[10]);  
HRESULT New2(double ar[10][20]);  
HRESULT New3(LPWStr ar[10]);  
```  
  
 **托管签名**  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.LPArray, SizeConst=10)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, SizeConst=200)> _  
   ar() As Double)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)> _  
   ar() As String)  
  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.LPArray, SizeConst=10)] int[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray, SizeConst=200)] double[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray,   
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)] String[] ar);  
```  
  
 虽然可以将 **size\_is** 或 **length\_is** 特性应用于接口定义语言 \(IDL\) 源中的数组以将大小传达给客户端，但是 Microsoft 接口定义语言 \(MIDL\) 编译器不会将该信息传播到类型库。  如果不知道大小，互操作封送处理服务就无法封送数组元素。  因此，变长数组被作为引用参数导入。  例如：  
  
 **非托管签名**  
  
```  
HRESULT New1(int ar[]);  
HRESULT New2(int ArSize, [size_is(ArSize)] double ar[]);  
HRESULT New3(int ElemCnt, [length_is(ElemCnt)] LPStr ar[]);  
```  
  
 **托管签名**  
  
```vb  
Sub New1(ByRef ar As Integer)  
Sub New2(ByRef ar As Double)  
Sub New3(ByRef ar As String)  
  
```  
  
```csharp  
void New1(ref int ar);    
void New2(ref double ar);    
void New3(ref String ar);   
```  
  
 可以通过编辑由 Tlbimp.exe 产生的 Microsoft 中间语言 \(MSIL\) 代码然后重新编译它来向封送拆收器提供数组大小。  有关如何修改 MSIL 代码的详细信息，请参见[自定义运行时可调用包装](http://msdn.microsoft.com/zh-cn/4652beaf-77d0-4f37-9687-ca193288c0be)。  若要指示数组中的元素数，请以下列方式之一将 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 类型应用于托管方法定义的数组参数：  
  
-   标识包含数组中的元素数的另一个参数。  参数是按位置标识的，开始的第一个参数的标识为数字 0。  \[Visual Basic\]  
  
    ```vb  
    Sub [New](ElemCnt As Integer, _  
       <MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
       ar() As Integer)  
  
    ```  
  
    ```csharp  
    void New(  
       int ElemCnt,   
       [MarshalAs(UnmanagedType.LPArray, SizeParamIndex=0)] int[] ar );  
    ```  
  
-   将数组的大小定义为常数。  例如：  
  
    ```vb  
    Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 在将数组从非托管代码封送到托管代码时，封送拆收器检查与参数相关联的 **MarshalAsAttribute** 以确定数组大小。  如果未指定数组大小，则只封送一个元素。  
  
> [!NOTE]
>  **MarshalAsAttribute** 不影响将托管数组封送到非托管代码。  在该方向上，数组大小是通过检查确定的。  无法封送托管数组的子集。  
  
 Interop 封送拆收器使用 **CoTaskMemAlloc** 和 **CoTaskMemFree** 方法分配并检索内存。  非托管代码所执行的内存分配也必须使用这些方法。  
  
<a name="cpcondefaultmarshalingforarraysanchor4"></a>   
## 将数组传递给 COM  
 所有托管数组都可以从托管代码传递给非托管代码。  根据对数组应用的托管类型和特性，可以将数组作为安全数组或 C 样式数组进行访问，如下表所示。  
  
|托管数组类型|导出为|  
|------------|---------|  
|**ELEMENT\_TYPE\_SZARRAY** **\<** *type* **\>**|<xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray\(** *type* **\)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> 类型在签名中提供。  秩始终为 1，下限始终为 0。  大小在运行时始终为已知。|  
|**ELEMENT\_TYPE\_ARRAY** **\<** *type* **\>** **\<** *rank* **\>**\[**\<** *bounds* **\>**\]|**UnmanagedType.SafeArray\(** *type* **\)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> 类型、秩和界限在签名中提供。  大小在运行时始终为已知。|  
|**ELEMENT\_TYPE\_CLASS** **\<**<xref:System.Array?displayProperty=fullName>**\>**|**UT\_Interface**<br /><br /> **UnmanagedType.SafeArray\(** *type* **\)**<br /><br /> 类型、秩、界限和大小在运行时始终为已知。|  
  
 在与包含 LPSTR 或 LPWSTR 的结构数组相关的 OLE 自动化方面有一个限制。  因此，必须将 **String** 字段作为 **UnmanagedType.BSTR** 封送。  否则，将引发异常。  
  
### ELEMENT\_TYPE\_SZARRAY  
 将包含 **ELEMENT\_TYPE\_SZARRAY** 参数（一维数组）的方法从 .NET 程序集导出到类型库时，该数组参数被转换为给定类型的 **SAFEARRAY**。  同样的转换规则也适用于数组元素类型。  托管数组的内容自动从托管内存复制到 **SAFEARRAY** 中。  例如：  
  
#### 托管签名  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### 非托管签名  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 安全数组的秩始终为 1，下限始终为 0。  大小在运行时由所传递的托管数组的大小确定。  
  
 还可以通过使用 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 特性将数组作为 C 样式数组封送。  例如：  
  
#### 托管签名  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As Long, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]   
   long [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]   
   String [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, ArraySubType=   
   UnmanagedType.LPStr, SizeParamIndex=1)]   
   String [] ar, int size );  
```  
  
#### 非托管签名  
  
```  
HRESULT New(long ar[]);   
HRESULT New(BSTR ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 虽然封送拆收器具有封送数组所需的长度信息，但是通常将数组长度作为单独参数传递以将长度传达给被调用方。  
  
### ELEMENT\_TYPE\_ARRAY  
 将包含 **ELEMENT\_TYPE\_ARRAY** 参数的方法从 .NET 程序集导出到类型库时，数组参数被转换为给定类型的 **SAFEARRAY**。  托管数组的内容自动从托管内存复制到 **SAFEARRAY** 中。  例如：  
  
#### 托管签名  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### 非托管签名  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 安全数组的秩、大小和界限在运行时由托管数组的特征确定。  
  
 还可以通过应用 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 特性将数组作为 C 样式数组封送。  例如：  
  
#### 托管签名  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex:=1)> _  
   ar(,) As Long, size As Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, _  
   ArraySubType:=UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar(,) As String, size As Integer)  
  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex=1)]   
   long [,] ar, int size );  
void New([MarshalAs(UnmanagedType.LPARRAY,   
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex=1)]   
   String [,] ar, int size );  
```  
  
#### 非托管签名  
  
```  
HRESULT New(long ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 不能封送嵌套的数组。  例如，当被用[类型库导出程序 \(Tlbexp.exe\)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) 导出时，下面的签名将生成错误。  
  
#### 托管签名  
  
```vb  
Sub [New](ar()()() As Long)  
  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### ELEMENT\_TYPE\_CLASS \<System.Array\>  
 将包含 <xref:System.Array?displayProperty=fullName> 参数的方法从 .NET 程序集导出到类型库中时，数组参数会转换为 **\_Array** 接口。  托管数组的内容只能通过 **\_Array** 接口的方法和属性访问。  还可以通过使用 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 特性将 **System.Array** 作为 **SAFEARRAY** 封送。  当作为安全数组封送时，数组元素被作为变量封送。  例如：  
  
#### 托管签名  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### 非托管签名  
  
```  
HRESULT New([in] _Array *ar);   
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### 结构内的数组  
 非托管结构可以包含嵌入数组。  默认情况下，这些嵌入数组字段作为 SAFEARRAY 封送。  在下面的示例中，`s1` 是直接在结构本身内部分配的嵌入数组。  
  
#### 非托管表示形式  
  
```  
struct MyStruct {  
    short s1[128];  
}  
```  
  
 数组可以作为 [UnmanagedType.ByValArray](frlrfSystemRuntimeInteropServicesUnmanagedTypeClassTopic) 封送，这需要设置 [MarshalAsAttribute.SizeConst](frlrfSystemRuntimeInteropServicesMarshalAsAttributeClassTopic) 字段。  大小只能被设置为常数。  下面的代码显示  `MyStruct` 的相应托管定义。  
  
```vb  
Public Structure <StructLayout(LayoutKind.Sequential)> MyStruct  
   Public <MarshalAs(UnmanagedType.ByValArray, SizeConst := 128)> _  
     s1() As Short  
End Structure  
  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public struct MyStruct {  
   [MarshalAs(UnmanagedType.ByValArray, SizeConst=128)] public short[] s1;  
}  
```  
  
## 请参阅  
 [默认封送处理行为](../../../docs/framework/interop/default-marshaling-behavior.md)   
 [可直接复制到本机结构中的类型和非直接复制到本机结构中的类型](../../../docs/framework/interop/blittable-and-non-blittable-types.md)   
 [Directional Attributes](http://msdn.microsoft.com/zh-cn/241ac5b5-928e-4969-8f58-1dbc048f9ea2)   
 [复制和锁定](../../../docs/framework/interop/copying-and-pinning.md)