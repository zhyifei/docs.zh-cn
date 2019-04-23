---
title: 提供程序清单规范
ms.date: 03/30/2017
ms.assetid: bb450b47-8951-4f99-9350-26f05a4d4e46
ms.openlocfilehash: 3d396f6ecfc0eb4a884e4af0d84ef65d18c5586c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169905"
---
# <a name="provider-manifest-specification"></a><span data-ttu-id="2c25d-102">提供程序清单规范</span><span class="sxs-lookup"><span data-stu-id="2c25d-102">Provider Manifest Specification</span></span>
<span data-ttu-id="2c25d-103">本节讨论数据存储提供程序如何可以支持数据存储中的类型和功能。</span><span class="sxs-lookup"><span data-stu-id="2c25d-103">This section discusses how a data store provider can support the types and functions in the data store.</span></span>  
  
 <span data-ttu-id="2c25d-104">实体服务独立于特定的数据存储提供程序进行操作，但仍允许数据提供程序显式定义模型、映射和查询与基础数据存储进行交互的方式。</span><span class="sxs-lookup"><span data-stu-id="2c25d-104">Entity Services operates independently of a specific data store provider yet still allows a data provider to explicitly define how models, mappings, and queries interact with an underlying data store.</span></span> <span data-ttu-id="2c25d-105">由于没有抽象层，只能在特定的数据存储或数据提供程序中以实体服务为目标。</span><span class="sxs-lookup"><span data-stu-id="2c25d-105">Without a layer of abstraction, Entity Services could only be targeted at a specific data store or data provider.</span></span>  
  
 <span data-ttu-id="2c25d-106">提供程序支持的类型由基础数据库直接或间接地提供支持。</span><span class="sxs-lookup"><span data-stu-id="2c25d-106">Types that the provider supports are directly or indirectly supported by the underlying database.</span></span> <span data-ttu-id="2c25d-107">这些类型不一定严格要求是存储类型，但提供程序使用这些类型支持[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2c25d-107">These types are not necessarily the exact store types, but the types the provider uses to support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="2c25d-108">提供程序/存储类型在实体数据模型 (EDM) 条目中进行了说明。</span><span class="sxs-lookup"><span data-stu-id="2c25d-108">Provider/store types are described in the Entity Data Model (EDM) terms.</span></span>  
  
 <span data-ttu-id="2c25d-109">在 EDM 条目中指定了数据存储支持的函数的参数和返回类型。</span><span class="sxs-lookup"><span data-stu-id="2c25d-109">Parameter and return types for the functions supported by the data store are specified in EDM terms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c25d-110">要求</span><span class="sxs-lookup"><span data-stu-id="2c25d-110">Requirements</span></span>  
 <span data-ttu-id="2c25d-111">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]和数据存储需要能够在已知类型中往返传递数据，而且不丢失或截断任何数据。</span><span class="sxs-lookup"><span data-stu-id="2c25d-111">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and the data store need to be able to pass data back and forth in known types without any data loss or truncation.</span></span>  
  
 <span data-ttu-id="2c25d-112">提供程序清单必须可由工具在设计时加载，而不必打开与数据存储的连接。</span><span class="sxs-lookup"><span data-stu-id="2c25d-112">The provider manifest must be loadable by tools at design time without having to open a connection to the data store.</span></span>  
  
 <span data-ttu-id="2c25d-113">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]是大小写敏感的但可能不是基础数据存储区。</span><span class="sxs-lookup"><span data-stu-id="2c25d-113">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] is case sensitive, but the underlying data store may not be.</span></span> <span data-ttu-id="2c25d-114">当在清单中定义和使用 EDM 项目（例如标识符和类型名称）时，这些项目必须使用[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]大小写区分。</span><span class="sxs-lookup"><span data-stu-id="2c25d-114">When EDM artifacts (identifiers and type names, for example) are defined and used in the manifest, they must use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] case sensitivity.</span></span> <span data-ttu-id="2c25d-115">如果可能区分大小写的数据存储元素出现在提供程序的清单中，则在提供程序清单中需要维持大小写区分。</span><span class="sxs-lookup"><span data-stu-id="2c25d-115">If data store elements that may be case sensitive appear in the provider manifest, that casing needs to be maintained in the provider manifest.</span></span>  
  
 <span data-ttu-id="2c25d-116">对于所有数据提供程序，[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]均需要一个提供程序清单。</span><span class="sxs-lookup"><span data-stu-id="2c25d-116">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] requires a provider manifest for all data providers.</span></span> <span data-ttu-id="2c25d-117">如果你尝试使用的提供程序没有提供程序清单与[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]，会收到错误。</span><span class="sxs-lookup"><span data-stu-id="2c25d-117">If you try to use a provider that does not have a provider manifest with the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you will get an error.</span></span>  
  
 <span data-ttu-id="2c25d-118">下表描述了在提供程序交互过程中引发异常时，[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]将引发的异常的种类。</span><span class="sxs-lookup"><span data-stu-id="2c25d-118">The following table describes the kinds of exceptions the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] would throw when exceptions arise through provider interaction:</span></span>  
  
|<span data-ttu-id="2c25d-119">问题</span><span class="sxs-lookup"><span data-stu-id="2c25d-119">Issue</span></span>|<span data-ttu-id="2c25d-120">例外</span><span class="sxs-lookup"><span data-stu-id="2c25d-120">Exception</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="2c25d-121">提供程序不支持 DbProviderServices 中的 GetProviderManifest。</span><span class="sxs-lookup"><span data-stu-id="2c25d-121">The Provider does not support GetProviderManifest in DbProviderServices.</span></span>|<span data-ttu-id="2c25d-122">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="2c25d-122">ProviderIncompatibleException</span></span>|  
|<span data-ttu-id="2c25d-123">缺少提供程序清单：在尝试检索提供程序清单时，提供程序返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="2c25d-123">Missing provider manifest: the provider returns `null` when attempting to retrieve the provider manifest.</span></span>|<span data-ttu-id="2c25d-124">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="2c25d-124">ProviderIncompatibleException</span></span>|  
|<span data-ttu-id="2c25d-125">无效的提供程序清单：在尝试检索提供程序清单时，提供程序返回无效的 XML。</span><span class="sxs-lookup"><span data-stu-id="2c25d-125">Invalid provider manifest: the provider returns invalid XML when attempting to retrieve the provider manifest.</span></span>|<span data-ttu-id="2c25d-126">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="2c25d-126">ProviderIncompatibleException</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="2c25d-127">方案</span><span class="sxs-lookup"><span data-stu-id="2c25d-127">Scenarios</span></span>  
 <span data-ttu-id="2c25d-128">提供程序应支持下面的方案：</span><span class="sxs-lookup"><span data-stu-id="2c25d-128">A provider should support the following scenarios:</span></span>  
  
### <a name="writing-a-provider-with-symmetric-type-mapping"></a><span data-ttu-id="2c25d-129">使用对称类型映射编写提供程序</span><span class="sxs-lookup"><span data-stu-id="2c25d-129">Writing a Provider with Symmetric Type Mapping</span></span>  
 <span data-ttu-id="2c25d-130">您可以编写一个提供程序[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]其中每个存储类型映射到单个 EDM 类型，无论映射方向。</span><span class="sxs-lookup"><span data-stu-id="2c25d-130">You can write a provider for the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] where each store type maps to a single EDM type, regardless of the mapping direction.</span></span> <span data-ttu-id="2c25d-131">对于具有非常简单的映射（与 EDM 类型对应）的提供程序类型，您可以使用对称解决方案，因为此类型系统很简单或者匹配 EDM 类型。</span><span class="sxs-lookup"><span data-stu-id="2c25d-131">For a provider type that has very simple mapping that corresponds with an EDM type, you can use a symmetric solution because the type system is simple or matches EDM types.</span></span>  
  
 <span data-ttu-id="2c25d-132">您可以利用提供程序的域的简单性，生成一个静态声明性提供程序清单。</span><span class="sxs-lookup"><span data-stu-id="2c25d-132">You can use the simplicity of their domain and produce a static declarative provider manifest.</span></span>  
  
 <span data-ttu-id="2c25d-133">编写具有两部分的 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="2c25d-133">You write an XML file that has two sections:</span></span>  
  
-   <span data-ttu-id="2c25d-134">以存储类型或函数的“EDM 对应项”的形式表示的提供程序类型列表。</span><span class="sxs-lookup"><span data-stu-id="2c25d-134">A list of provider types expressed in terms of the "EDM counterpart" of a store type or function.</span></span> <span data-ttu-id="2c25d-135">存储类型具有对应的 EDM 类型。</span><span class="sxs-lookup"><span data-stu-id="2c25d-135">Store types have counterpart EDM types.</span></span> <span data-ttu-id="2c25d-136">存储函数具有对应的 EDM 函数。</span><span class="sxs-lookup"><span data-stu-id="2c25d-136">Store functions have corresponding EDM functions.</span></span> <span data-ttu-id="2c25d-137">例如，varchar 是一个 SQL Server 类型，但对应的 EDM 类型是字符串。</span><span class="sxs-lookup"><span data-stu-id="2c25d-137">For example, varchar is a SQL Server type but the corresponding EDM type is string.</span></span>  
  
-   <span data-ttu-id="2c25d-138">提供程序支持的函数列表，其中的参数和返回类型用 EDM 术语表示。</span><span class="sxs-lookup"><span data-stu-id="2c25d-138">A list of functions supported by the provider where parameter and return types are expressed in EDM terms.</span></span>  
  
### <a name="writing-a-provider-with-asymmetric-type-mapping"></a><span data-ttu-id="2c25d-139">使用非对称类型映射编写提供程序</span><span class="sxs-lookup"><span data-stu-id="2c25d-139">Writing a Provider with Asymmetric Type Mapping</span></span>  
 <span data-ttu-id="2c25d-140">在编写[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]的数据存储提供程序时，某些类型的 EDM 到提供程序的类型映射可能与提供程序到 EDM 的类型映射不同。</span><span class="sxs-lookup"><span data-stu-id="2c25d-140">When writing a data store provider for the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], the EDM-to-provider type mapping for some types may be different from provider-to-EDM type mapping.</span></span> <span data-ttu-id="2c25d-141">例如，无限制的 EDM PrimitiveTypeKind.String 可能会映射到提供程序上的 nvarchar(4000)，而 nvarchar(4000) 将映射到 EDM PrimitiveTypeKind.String(MaxLength=4000)。</span><span class="sxs-lookup"><span data-stu-id="2c25d-141">For instance, unbounded EDM PrimitiveTypeKind.String may map to nvarchar(4000) on the provider, while nvarchar(4000) maps to the EDM PrimitiveTypeKind.String(MaxLength=4000).</span></span>  
  
 <span data-ttu-id="2c25d-142">编写具有两部分的 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="2c25d-142">You write an XML file that has two sections:</span></span>  
  
-   <span data-ttu-id="2c25d-143">提供程序类型的列表以 EDM 表示，并定义了两个方向的映射：EDM 到提供程序和提供程序到 EDM。</span><span class="sxs-lookup"><span data-stu-id="2c25d-143">A list of provider types expressed in EDM terms and define mapping for both direction: EDM-to-provider and provider-to-EDM.</span></span>  
  
-   <span data-ttu-id="2c25d-144">提供程序支持的函数列表，其中的参数和返回类型用 EDM 术语表示。</span><span class="sxs-lookup"><span data-stu-id="2c25d-144">A list of functions supported by the provider where parameter and return types are expressed in EDM terms.</span></span>  
  
## <a name="provider-manifest-discoverability"></a><span data-ttu-id="2c25d-145">提供程序清单的可发现性</span><span class="sxs-lookup"><span data-stu-id="2c25d-145">Provider Manifest Discoverability</span></span>  
 <span data-ttu-id="2c25d-146">清单可以由实体服务中的若干组件类型（例如“工具”或“查询”）间接地使用，但更多的是通过使用数据存储元数据加载程序由元数据直接利用。</span><span class="sxs-lookup"><span data-stu-id="2c25d-146">The manifest is used indirectly by several component types in Entity Services (for example Tools or Query) but more directly leveraged by metadata through the use of the data store metadata loader.</span></span>  
  
 <span data-ttu-id="2c25d-147">![dfb3d02b&#45;7a8c&#45;4d51&#45;ac5a&#45;a73d8aa145e6](../../../../../docs/framework/data/adonet/ef/media/dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6.gif "dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6")</span><span class="sxs-lookup"><span data-stu-id="2c25d-147">![dfb3d02b&#45;7a8c&#45;4d51&#45;ac5a&#45;a73d8aa145e6](../../../../../docs/framework/data/adonet/ef/media/dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6.gif "dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6")</span></span>  
  
 <span data-ttu-id="2c25d-148">但是，给定的提供程序可能支持不同的存储或相同存储的不同版本。</span><span class="sxs-lookup"><span data-stu-id="2c25d-148">However, a given provider may support different stores or different versions of the same store.</span></span> <span data-ttu-id="2c25d-149">因此，对于每个支持的数据存储，提供程序必须报告不同的清单。</span><span class="sxs-lookup"><span data-stu-id="2c25d-149">Therefore, a provider must report a different manifest for each supported data store.</span></span>  
  
### <a name="provider-manifest-token"></a><span data-ttu-id="2c25d-150">提供程序清单标记</span><span class="sxs-lookup"><span data-stu-id="2c25d-150">Provider Manifest Token</span></span>  
 <span data-ttu-id="2c25d-151">当打开数据存储连接时，提供程序可以查询信息以返回正确的清单。</span><span class="sxs-lookup"><span data-stu-id="2c25d-151">When a data store connection is opened, the provider can query for information to return the right manifest.</span></span> <span data-ttu-id="2c25d-152">在无法获取连接信息的脱机方案中，或者在无法连接到存储的情况下，上述方法可能不可行。</span><span class="sxs-lookup"><span data-stu-id="2c25d-152">This may not be possible in offline scenarios where connection information is not available or when it is not possible to connect to the store.</span></span> <span data-ttu-id="2c25d-153">通过使用 .ssdl 文件中的 `ProviderManifestToken` 元素的 `Schema` 特性可标识清单。</span><span class="sxs-lookup"><span data-stu-id="2c25d-153">Identify the manifest by using the `ProviderManifestToken` attribute of the `Schema` element in the .ssdl file.</span></span> <span data-ttu-id="2c25d-154">此特性没有必需的格式要求，提供程序可选择所需的最少信息来标识清单，而无需打开与存储的连接。</span><span class="sxs-lookup"><span data-stu-id="2c25d-154">There is no required format for this attribute; the provider chooses the minimum information needed to identify a manifest without opening a connection to the store.</span></span>  
  
 <span data-ttu-id="2c25d-155">例如：</span><span class="sxs-lookup"><span data-stu-id="2c25d-155">For example:</span></span>  
  
```xml  
<Schema Namespace="Northwind" Provider="System.Data.SqlClient" ProviderManifestToken="2005" xmlns:edm="http://schemas.microsoft.com/ado/2006/04/edm/ssdl" xmlns="http://schemas.microsoft.com/ado/2006/04/edm/ssdl">  
```  
  
## <a name="provider-manifest-programming-model"></a><span data-ttu-id="2c25d-156">提供程序清单编程模型</span><span class="sxs-lookup"><span data-stu-id="2c25d-156">Provider Manifest Programming Model</span></span>  
 <span data-ttu-id="2c25d-157">提供程序派生自 <xref:System.Data.Common.DbXmlEnabledProviderManifest>，这使得它们可以通过声明方式指定其清单。</span><span class="sxs-lookup"><span data-stu-id="2c25d-157">Providers derive from <xref:System.Data.Common.DbXmlEnabledProviderManifest>, which allows them to specify their manifests declaratively.</span></span> <span data-ttu-id="2c25d-158">下图显示了提供程序的类层次结构：</span><span class="sxs-lookup"><span data-stu-id="2c25d-158">The following illustration shows the class hierarchy of a provider:</span></span>  
  
 <span data-ttu-id="2c25d-159">![None](../../../../../docs/framework/data/adonet/ef/media/d541eba3-2ee6-4cd1-88f5-89d0b2582a6c.gif "d541eba3-2ee6-4cd1-88f5-89d0b2582a6c")</span><span class="sxs-lookup"><span data-stu-id="2c25d-159">![None](../../../../../docs/framework/data/adonet/ef/media/d541eba3-2ee6-4cd1-88f5-89d0b2582a6c.gif "d541eba3-2ee6-4cd1-88f5-89d0b2582a6c")</span></span>  
  
### <a name="discoverability-api"></a><span data-ttu-id="2c25d-160">可发现性 API</span><span class="sxs-lookup"><span data-stu-id="2c25d-160">Discoverability API</span></span>  
 <span data-ttu-id="2c25d-161">通过使用数据存储连接或提供程序清单标记，存储元数据加载程序 (StoreItemCollection) 可加载提供程序清单。</span><span class="sxs-lookup"><span data-stu-id="2c25d-161">The provider manifest is loaded by the Store Metadata loader (StoreItemCollection), either by using a data store connection or a provider manifest token.</span></span>  
  
#### <a name="using-a-data-store-connection"></a><span data-ttu-id="2c25d-162">使用数据存储连接</span><span class="sxs-lookup"><span data-stu-id="2c25d-162">Using a Data Store Connection</span></span>  
 <span data-ttu-id="2c25d-163">当数据存储连接可用时，调用 DbProvderServices.GetProviderManifestToken 以返回传递给 GetProviderManifest 方法的标记，GetProviderManifest 方法返回 DbProviderManifest。</span><span class="sxs-lookup"><span data-stu-id="2c25d-163">When the data store connection is available, call DbProvderServices.GetProviderManifestToken to return the token that is passed to the GetProviderManifest method, which returns DbProviderManifest.</span></span> <span data-ttu-id="2c25d-164">此方法委托给提供程序的 GetDbProviderManifestToken 实现。</span><span class="sxs-lookup"><span data-stu-id="2c25d-164">This method delegates to the provider's implementation of GetDbProviderManifestToken.</span></span>  
  
```  
public string GetProviderManifestToken(DbConnection connection);  
public DbProviderManifest GetProviderManifest(string manifestToken);  
```  
  
#### <a name="using-a-provider-manifest-token"></a><span data-ttu-id="2c25d-165">使用提供程序清单标记</span><span class="sxs-lookup"><span data-stu-id="2c25d-165">Using a Provider Manifest Token</span></span>  
 <span data-ttu-id="2c25d-166">对于脱机方案，此标记从 SSDL 表示形式中选取。</span><span class="sxs-lookup"><span data-stu-id="2c25d-166">For the offline scenario, the token is picked from SSDL representation.</span></span> <span data-ttu-id="2c25d-167">SSDL 允许您指定 ProviderManifestToken (请参阅[架构元素 (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl)有关详细信息)。</span><span class="sxs-lookup"><span data-stu-id="2c25d-167">The SSDL allows you to specify a ProviderManifestToken (see [Schema Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl) for more information).</span></span> <span data-ttu-id="2c25d-168">例如，如果无法打开某个连接，则 SSDL 会具有一个提供程序清单标记，用于指定有关清单的信息。</span><span class="sxs-lookup"><span data-stu-id="2c25d-168">For example, if a connection cannot be opened, the SSDL has a provider manifest token that specifies information about the manifest.</span></span>  
  
```  
public DbProviderManifest GetProviderManifest(string manifestToken);  
```  
  
### <a name="provider-manifest-schema"></a><span data-ttu-id="2c25d-169">提供程序清单架构</span><span class="sxs-lookup"><span data-stu-id="2c25d-169">Provider Manifest Schema</span></span>  
 <span data-ttu-id="2c25d-170">为每个提供程序定义的信息架构包含元数据要使用的静态信息：</span><span class="sxs-lookup"><span data-stu-id="2c25d-170">The schema of information defined for each provider contains the static information to be consumed by metadata:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema elementFormDefault="qualified"  
   xmlns:xs="http://www.w3.org/2001/XMLSchema"  
   targetNamespace="http://schemas.microsoft.com/ado/2006/04/edm/providermanifest"  
   xmlns:pm="http://schemas.microsoft.com/ado/2006/04/edm/providermanifest">  
  
  <xs:element name="ProviderManifest">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="Types" type="pm:TTypes" minOccurs="1" maxOccurs="1" />  
        <xs:element name="Functions" type="pm:TFunctions" minOccurs="0" maxOccurs="1"/>  
      </xs:sequence>  
      <xs:attribute name="Namespace" type="xs:string" use="required"/>  
    </xs:complexType>  
  </xs:element>  
  <xs:complexType name="TVersion">  
    <xs:attribute name="Major" type="xs:int" use="required" />  
    <xs:attribute name="Minor" type="xs:int" use="required" />  
    <xs:attribute name="Build" type="xs:int" use="required" />  
    <xs:attribute name="Revision" type="xs:int" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TIntegerFacetDescription">  
    <xs:attribute name="Minimum" type="xs:int" use="optional" />  
    <xs:attribute name="Maximum" type="xs:int" use="optional" />  
    <xs:attribute name="DefaultValue" type="xs:int" use="optional" />  
    <xs:attribute name="Constant" type="xs:boolean" default="false" />  
  </xs:complexType>  
  
  <xs:complexType name="TBooleanFacetDescription">  
    <xs:attribute name="DefaultValue" type="xs:boolean" use="optional" />  
    <xs:attribute name="Constant" type="xs:boolean" default="true" />  
  </xs:complexType>  
  
  <xs:complexType name="TDateTimeFacetDescription">  
    <xs:attribute name="Constant" type="xs:boolean" default="false" />  
  </xs:complexType>  
  
  <xs:complexType name="TFacetDescriptions">  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="Precision" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="Scale" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="MaxLength" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="Unicode" minOccurs="0" maxOccurs="1" type="pm:TBooleanFacetDescription"/>  
      <xs:element name="FixedLength" minOccurs="0" maxOccurs="1" type="pm:TBooleanFacetDescription"/>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:complexType name="TType">  
    <xs:sequence>  
      <xs:element name="FacetDescriptions" type="pm:TFacetDescriptions" minOccurs="0" maxOccurs="1"/>  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="required"/>  
    <xs:attribute name="PrimitiveTypeKind" type="pm:TPrimitiveTypeKind" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TTypes">  
    <xs:sequence>  
      <xs:element name="Type" type="pm:TType" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:sequence>  
  </xs:complexType>  
  
  <xs:attributeGroup name="TFacetAttribute">  
    <xs:attribute name="Precision" type="xs:int" use="optional"/>  
    <xs:attribute name="Scale" type="xs:int" use="optional"/>  
    <xs:attribute name="MaxLength" type="xs:int" use="optional"/>  
    <xs:attribute name="Unicode" type="xs:boolean" use="optional"/>  
    <xs:attribute name="FixedLength" type="xs:boolean" use="optional"/>  
  </xs:attributeGroup>  
  
  <xs:complexType name="TFunctionParameter">  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="Type" type="xs:string" use="required" />  
    <xs:attributeGroup ref="pm:TFacetAttribute" />  
    <xs:attribute name="Mode" type="pm:TParameterDirection" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TReturnType">  
    <xs:attribute name="Type" type="xs:string" use="required" />  
    <xs:attributeGroup ref="pm:TFacetAttribute" />  
  </xs:complexType>  
  
  <xs:complexType name="TFunction">  
    <xs:choice minOccurs="0" maxOccurs ="unbounded">  
      <xs:element name ="ReturnType" type="pm:TReturnType" minOccurs="0" maxOccurs="1" />  
      <xs:element name="Parameter" type="pm:TFunctionParameter" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:choice>  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="Aggregate" type="xs:boolean" use="optional" />  
    <xs:attribute name="BuiltIn" type="xs:boolean" use="optional" />  
    <xs:attribute name="StoreFunctionName" type="xs:string" use="optional" />  
    <xs:attribute name="NiladicFunction" type="xs:boolean" use="optional" />  
    <xs:attribute name="ParameterTypeSemantics" type="pm:TParameterTypeSemantics" use="optional" default="AllowImplicitConversion" />  
  </xs:complexType>  
  
  <xs:complexType name="TFunctions">  
    <xs:sequence>  
      <xs:element name="Function" type="pm:TFunction" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:sequence>  
  </xs:complexType>  
  
  <xs:simpleType name="TPrimitiveTypeKind">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Binary"/>  
      <xs:enumeration value="Boolean"/>  
      <xs:enumeration value="Byte"/>  
      <xs:enumeration value="Decimal"/>  
      <xs:enumeration value="DateTime"/>  
      <xs:enumeration value="Time"/>  
      <xs:enumeration value="DateTimeOffset"/>          
      <xs:enumeration value="Double"/>  
      <xs:enumeration value="Guid"/>  
      <xs:enumeration value="Single"/>  
      <xs:enumeration value="SByte"/>  
      <xs:enumeration value="Int16"/>  
      <xs:enumeration value="Int32"/>  
      <xs:enumeration value="Int64"/>  
      <xs:enumeration value="String"/>  
    </xs:restriction>  
  </xs:simpleType>  
  
  <xs:simpleType name="TParameterDirection">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="In"/>  
      <xs:enumeration value="Out"/>  
      <xs:enumeration value="InOut"/>  
    </xs:restriction>  
  </xs:simpleType>  
  
  <xs:simpleType name="TParameterTypeSemantics">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="ExactMatchOnly" />  
      <xs:enumeration value="AllowImplicitPromotion" />  
      <xs:enumeration value="AllowImplicitConversion" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
#### <a name="types-node"></a><span data-ttu-id="2c25d-171">Types 节点</span><span class="sxs-lookup"><span data-stu-id="2c25d-171">Types Node</span></span>  
 <span data-ttu-id="2c25d-172">提供程序清单中的 Types 节点包含有关数据存储区本身支持的或通过提供程序支持的 Type 的信息。</span><span class="sxs-lookup"><span data-stu-id="2c25d-172">The Types node in the provider manifest contains information about the Types that are supported natively by the data store or through the provider.</span></span>  
  
##### <a name="type-node"></a><span data-ttu-id="2c25d-173">Type 节点</span><span class="sxs-lookup"><span data-stu-id="2c25d-173">Type Node</span></span>  
 <span data-ttu-id="2c25d-174">每个 Type 节点以 EDM 的形式定义一个提供程序类型。</span><span class="sxs-lookup"><span data-stu-id="2c25d-174">Each Type node defines a provider type in terms of EDM.</span></span> <span data-ttu-id="2c25d-175">Type 节点描述提供程序类型的名称、与其映射到的模型类型相关的信息以及用于描述类型映射的各个方面。</span><span class="sxs-lookup"><span data-stu-id="2c25d-175">The Type node describes the name of the provider type, and information related to the model type it maps to and facets to describe that type mapping.</span></span>  
  
 <span data-ttu-id="2c25d-176">为了在提供程序清单中表示此类型信息，每个 TypeInformation 声明必须为每个 Type 定义几个方面的说明：</span><span class="sxs-lookup"><span data-stu-id="2c25d-176">In order to express this type information in the provider manifest, each TypeInformation declaration must define several facet descriptions for each Type:</span></span>  
  
|<span data-ttu-id="2c25d-177">特性名</span><span class="sxs-lookup"><span data-stu-id="2c25d-177">Attribute Name</span></span>|<span data-ttu-id="2c25d-178">数据类型</span><span class="sxs-lookup"><span data-stu-id="2c25d-178">Data Type</span></span>|<span data-ttu-id="2c25d-179">必需</span><span class="sxs-lookup"><span data-stu-id="2c25d-179">Required</span></span>|<span data-ttu-id="2c25d-180">默认值</span><span class="sxs-lookup"><span data-stu-id="2c25d-180">Default Value</span></span>|<span data-ttu-id="2c25d-181">描述</span><span class="sxs-lookup"><span data-stu-id="2c25d-181">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="2c25d-182">名称</span><span class="sxs-lookup"><span data-stu-id="2c25d-182">Name</span></span>|<span data-ttu-id="2c25d-183">String</span><span class="sxs-lookup"><span data-stu-id="2c25d-183">String</span></span>|<span data-ttu-id="2c25d-184">是</span><span class="sxs-lookup"><span data-stu-id="2c25d-184">Yes</span></span>|<span data-ttu-id="2c25d-185">n/a</span><span class="sxs-lookup"><span data-stu-id="2c25d-185">n/a</span></span>|<span data-ttu-id="2c25d-186">提供程序特定的数据类型名称</span><span class="sxs-lookup"><span data-stu-id="2c25d-186">Provider-specific data type name</span></span>|  
|<span data-ttu-id="2c25d-187">PrimitiveTypeKind</span><span class="sxs-lookup"><span data-stu-id="2c25d-187">PrimitiveTypeKind</span></span>|<span data-ttu-id="2c25d-188">PrimitiveTypeKind</span><span class="sxs-lookup"><span data-stu-id="2c25d-188">PrimitiveTypeKind</span></span>|<span data-ttu-id="2c25d-189">是</span><span class="sxs-lookup"><span data-stu-id="2c25d-189">Yes</span></span>|<span data-ttu-id="2c25d-190">n/a</span><span class="sxs-lookup"><span data-stu-id="2c25d-190">n/a</span></span>|<span data-ttu-id="2c25d-191">EDM 类型名称</span><span class="sxs-lookup"><span data-stu-id="2c25d-191">EDM type name</span></span>|  
  
###### <a name="function-node"></a><span data-ttu-id="2c25d-192">Function 节点</span><span class="sxs-lookup"><span data-stu-id="2c25d-192">Function Node</span></span>  
 <span data-ttu-id="2c25d-193">每个 Function 定义一个可通过提供程序使用的函数。</span><span class="sxs-lookup"><span data-stu-id="2c25d-193">Each Function defines a single function available through the provider.</span></span>  
  
|<span data-ttu-id="2c25d-194">特性名</span><span class="sxs-lookup"><span data-stu-id="2c25d-194">Attribute Name</span></span>|<span data-ttu-id="2c25d-195">数据类型</span><span class="sxs-lookup"><span data-stu-id="2c25d-195">Data Type</span></span>|<span data-ttu-id="2c25d-196">必需</span><span class="sxs-lookup"><span data-stu-id="2c25d-196">Required</span></span>|<span data-ttu-id="2c25d-197">默认值</span><span class="sxs-lookup"><span data-stu-id="2c25d-197">Default Value</span></span>|<span data-ttu-id="2c25d-198">描述</span><span class="sxs-lookup"><span data-stu-id="2c25d-198">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="2c25d-199">名称</span><span class="sxs-lookup"><span data-stu-id="2c25d-199">Name</span></span>|<span data-ttu-id="2c25d-200">String</span><span class="sxs-lookup"><span data-stu-id="2c25d-200">String</span></span>|<span data-ttu-id="2c25d-201">是</span><span class="sxs-lookup"><span data-stu-id="2c25d-201">Yes</span></span>|<span data-ttu-id="2c25d-202">n/a</span><span class="sxs-lookup"><span data-stu-id="2c25d-202">n/a</span></span>|<span data-ttu-id="2c25d-203">函数的标识符/名称</span><span class="sxs-lookup"><span data-stu-id="2c25d-203">Identifier/name of the function</span></span>|  
|<span data-ttu-id="2c25d-204">ReturnType</span><span class="sxs-lookup"><span data-stu-id="2c25d-204">ReturnType</span></span>|<span data-ttu-id="2c25d-205">String</span><span class="sxs-lookup"><span data-stu-id="2c25d-205">String</span></span>|<span data-ttu-id="2c25d-206">否</span><span class="sxs-lookup"><span data-stu-id="2c25d-206">No</span></span>|<span data-ttu-id="2c25d-207">Void</span><span class="sxs-lookup"><span data-stu-id="2c25d-207">Void</span></span>|<span data-ttu-id="2c25d-208">函数的 EDM 返回类型</span><span class="sxs-lookup"><span data-stu-id="2c25d-208">The EDM return type of the function</span></span>|  
|<span data-ttu-id="2c25d-209">聚合</span><span class="sxs-lookup"><span data-stu-id="2c25d-209">Aggregate</span></span>|<span data-ttu-id="2c25d-210">Boolean</span><span class="sxs-lookup"><span data-stu-id="2c25d-210">Boolean</span></span>|<span data-ttu-id="2c25d-211">否</span><span class="sxs-lookup"><span data-stu-id="2c25d-211">No</span></span>|<span data-ttu-id="2c25d-212">False</span><span class="sxs-lookup"><span data-stu-id="2c25d-212">False</span></span>|<span data-ttu-id="2c25d-213">如果函数为聚合函数，则为 True。</span><span class="sxs-lookup"><span data-stu-id="2c25d-213">True if the function is an aggregate function</span></span>|  
|<span data-ttu-id="2c25d-214">BuiltIn</span><span class="sxs-lookup"><span data-stu-id="2c25d-214">BuiltIn</span></span>|<span data-ttu-id="2c25d-215">Boolean</span><span class="sxs-lookup"><span data-stu-id="2c25d-215">Boolean</span></span>|<span data-ttu-id="2c25d-216">否</span><span class="sxs-lookup"><span data-stu-id="2c25d-216">No</span></span>|<span data-ttu-id="2c25d-217">True</span><span class="sxs-lookup"><span data-stu-id="2c25d-217">True</span></span>|<span data-ttu-id="2c25d-218">如果函数内置于数据存储中，则返回 True</span><span class="sxs-lookup"><span data-stu-id="2c25d-218">True if the function is built into the data store</span></span>|  
|<span data-ttu-id="2c25d-219">StoreFunctionName</span><span class="sxs-lookup"><span data-stu-id="2c25d-219">StoreFunctionName</span></span>|<span data-ttu-id="2c25d-220">String</span><span class="sxs-lookup"><span data-stu-id="2c25d-220">String</span></span>|<span data-ttu-id="2c25d-221">否</span><span class="sxs-lookup"><span data-stu-id="2c25d-221">No</span></span>|<span data-ttu-id="2c25d-222">\<名称 ></span><span class="sxs-lookup"><span data-stu-id="2c25d-222">\<Name></span></span>|<span data-ttu-id="2c25d-223">数据存储中的函数名称。</span><span class="sxs-lookup"><span data-stu-id="2c25d-223">Function Name in the data store.</span></span>  <span data-ttu-id="2c25d-224">考虑了函数名称的重定向级别。</span><span class="sxs-lookup"><span data-stu-id="2c25d-224">Allows for a level of redirection of function names.</span></span>|  
|<span data-ttu-id="2c25d-225">NiladicFunction</span><span class="sxs-lookup"><span data-stu-id="2c25d-225">NiladicFunction</span></span>|<span data-ttu-id="2c25d-226">Boolean</span><span class="sxs-lookup"><span data-stu-id="2c25d-226">Boolean</span></span>|<span data-ttu-id="2c25d-227">否</span><span class="sxs-lookup"><span data-stu-id="2c25d-227">No</span></span>|<span data-ttu-id="2c25d-228">False</span><span class="sxs-lookup"><span data-stu-id="2c25d-228">False</span></span>|<span data-ttu-id="2c25d-229">如果函数不需要任何参数且在调用时不使用任何参数，则返回 True。</span><span class="sxs-lookup"><span data-stu-id="2c25d-229">True if the function does not require parameters and is called without any parameters</span></span>|  
|<span data-ttu-id="2c25d-230">ParameterType</span><span class="sxs-lookup"><span data-stu-id="2c25d-230">ParameterType</span></span><br /><br /> <span data-ttu-id="2c25d-231">语义</span><span class="sxs-lookup"><span data-stu-id="2c25d-231">Semantics</span></span>|<span data-ttu-id="2c25d-232">ParameterSemantics</span><span class="sxs-lookup"><span data-stu-id="2c25d-232">ParameterSemantics</span></span>|<span data-ttu-id="2c25d-233">否</span><span class="sxs-lookup"><span data-stu-id="2c25d-233">No</span></span>|<span data-ttu-id="2c25d-234">AllowImplicit</span><span class="sxs-lookup"><span data-stu-id="2c25d-234">AllowImplicit</span></span><br /><br /> <span data-ttu-id="2c25d-235">转换</span><span class="sxs-lookup"><span data-stu-id="2c25d-235">Conversion</span></span>|<span data-ttu-id="2c25d-236">有关查询管道应如何处理参数类型替换的选项：</span><span class="sxs-lookup"><span data-stu-id="2c25d-236">Choice of how the query pipeline should deal with parameter type substitution:</span></span><br /><br /> <span data-ttu-id="2c25d-237">-   ExactMatchOnly</span><span class="sxs-lookup"><span data-stu-id="2c25d-237">-   ExactMatchOnly</span></span><br /><span data-ttu-id="2c25d-238">-   AllowImplicitPromotion</span><span class="sxs-lookup"><span data-stu-id="2c25d-238">-   AllowImplicitPromotion</span></span><br /><span data-ttu-id="2c25d-239">-   AllowImplicitConversion</span><span class="sxs-lookup"><span data-stu-id="2c25d-239">-   AllowImplicitConversion</span></span>|  
  
 <span data-ttu-id="2c25d-240">**参数节点**</span><span class="sxs-lookup"><span data-stu-id="2c25d-240">**Parameters Node**</span></span>  
  
 <span data-ttu-id="2c25d-241">每个函数都具有包含一个或多个 Parameter 节点的集合。</span><span class="sxs-lookup"><span data-stu-id="2c25d-241">Each function has a collection of one or more Parameter nodes.</span></span>  
  
|<span data-ttu-id="2c25d-242">特性名</span><span class="sxs-lookup"><span data-stu-id="2c25d-242">Attribute Name</span></span>|<span data-ttu-id="2c25d-243">数据类型</span><span class="sxs-lookup"><span data-stu-id="2c25d-243">Data Type</span></span>|<span data-ttu-id="2c25d-244">必需</span><span class="sxs-lookup"><span data-stu-id="2c25d-244">Required</span></span>|<span data-ttu-id="2c25d-245">默认值</span><span class="sxs-lookup"><span data-stu-id="2c25d-245">Default Value</span></span>|<span data-ttu-id="2c25d-246">描述</span><span class="sxs-lookup"><span data-stu-id="2c25d-246">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="2c25d-247">名称</span><span class="sxs-lookup"><span data-stu-id="2c25d-247">Name</span></span>|<span data-ttu-id="2c25d-248">String</span><span class="sxs-lookup"><span data-stu-id="2c25d-248">String</span></span>|<span data-ttu-id="2c25d-249">是</span><span class="sxs-lookup"><span data-stu-id="2c25d-249">Yes</span></span>|<span data-ttu-id="2c25d-250">n/a</span><span class="sxs-lookup"><span data-stu-id="2c25d-250">n/a</span></span>|<span data-ttu-id="2c25d-251">参数的标识符/名称。</span><span class="sxs-lookup"><span data-stu-id="2c25d-251">Identifier/name of the parameter.</span></span>|  
|<span data-ttu-id="2c25d-252">类型</span><span class="sxs-lookup"><span data-stu-id="2c25d-252">Type</span></span>|<span data-ttu-id="2c25d-253">String</span><span class="sxs-lookup"><span data-stu-id="2c25d-253">String</span></span>|<span data-ttu-id="2c25d-254">是</span><span class="sxs-lookup"><span data-stu-id="2c25d-254">Yes</span></span>|<span data-ttu-id="2c25d-255">n/a</span><span class="sxs-lookup"><span data-stu-id="2c25d-255">n/a</span></span>|<span data-ttu-id="2c25d-256">参数的 EDM 类型。</span><span class="sxs-lookup"><span data-stu-id="2c25d-256">The EDM type of the parameter.</span></span>|  
|<span data-ttu-id="2c25d-257">模式</span><span class="sxs-lookup"><span data-stu-id="2c25d-257">Mode</span></span>|<span data-ttu-id="2c25d-258">参数</span><span class="sxs-lookup"><span data-stu-id="2c25d-258">Parameter</span></span><br /><br /> <span data-ttu-id="2c25d-259">方向</span><span class="sxs-lookup"><span data-stu-id="2c25d-259">Direction</span></span>|<span data-ttu-id="2c25d-260">是</span><span class="sxs-lookup"><span data-stu-id="2c25d-260">Yes</span></span>|<span data-ttu-id="2c25d-261">n/a</span><span class="sxs-lookup"><span data-stu-id="2c25d-261">n/a</span></span>|<span data-ttu-id="2c25d-262">参数的方向：</span><span class="sxs-lookup"><span data-stu-id="2c25d-262">Direction of parameter:</span></span><br /><br /> <span data-ttu-id="2c25d-263">-在</span><span class="sxs-lookup"><span data-stu-id="2c25d-263">-   in</span></span><br /><span data-ttu-id="2c25d-264">-out</span><span class="sxs-lookup"><span data-stu-id="2c25d-264">-   out</span></span><br /><span data-ttu-id="2c25d-265">-inout</span><span class="sxs-lookup"><span data-stu-id="2c25d-265">-   inout</span></span>|  
  
##### <a name="namespace-attribute"></a><span data-ttu-id="2c25d-266">Namespace 属性</span><span class="sxs-lookup"><span data-stu-id="2c25d-266">Namespace Attribute</span></span>  
 <span data-ttu-id="2c25d-267">每个数据存储提供程序必须为清单中定义的信息定义一个命名空间或一组命名空间。</span><span class="sxs-lookup"><span data-stu-id="2c25d-267">Each data store provider must define a namespace or group of namespaces for information defined in the manifest.</span></span> <span data-ttu-id="2c25d-268">此命名空间可在 Entity SQL 查询中用来解析函数和类型的名称。</span><span class="sxs-lookup"><span data-stu-id="2c25d-268">This namespace can be used in Entity SQL queries to resolve names of functions and types.</span></span> <span data-ttu-id="2c25d-269">例如：SqlServer。</span><span class="sxs-lookup"><span data-stu-id="2c25d-269">For instance: SqlServer.</span></span> <span data-ttu-id="2c25d-270">此命名空间必须与规范命名空间 EDM 不同，EDM 是由实体服务为 Entity SQL 查询要支持的标准函数定义的。</span><span class="sxs-lookup"><span data-stu-id="2c25d-270">That namespace must be different from the canonical namespace, EDM, defined by Entity Services for standard functions to be supported by Entity SQL queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c25d-271">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c25d-271">See also</span></span>

- [<span data-ttu-id="2c25d-272">编写实体框架数据提供程序</span><span class="sxs-lookup"><span data-stu-id="2c25d-272">Writing an Entity Framework Data Provider</span></span>](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
