---
title: WCF 和国际化域名
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: 24b7af660d5fd9629639d3b63d605ef619dcf009
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="wcf-and-internationalized-domain-names"></a>WCF 和国际化域名
添加了允许使用带有国际化域名 (IDN) 的 WCF 服务的支持。 国际化域名称是包含非 ASCII 字符的域名。 这种支持包括能够承载具有 IDN 名称的 WCF 服务以及 WCF 客户端，以便与具有 IDN 名称的 Web 服务进行对话。  
  
## <a name="systemuri-and-idn"></a>System.Uri 和 IDN  
 <xref:System.Uri> 具有两个属性：<xref:System.Uri.Host%2A> 和 <xref:System.Uri.DnsSafeHost%2A>。 根据 IDN 配置设置，这些属性包含 Unicode 或 Punycode 值。  
  
 使用下面的 XML 在应用程序的配置文件中启用 IDN  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 \<Idn > 元素包含 enabled 的属性都被设置为下列值之一：  
  
1.  "无"  
  
2.  "AllExceptIntranet"  
  
3.  "全部"  
  
 在 IDN 设置设为"None"，Uri.Host 或 Uri.DnsSafeHost 会不进行任何转换。 在 IDN 设置设为"All"时，uri。主机保留 Unicode 和 uri。DnsSafeHost 转换为 Punycode。 在 IDN 设置设为"AllExceptIntranet"，uri。DnsSafeHost 都会转换为 Punycode 用于 internet 地址，并且保留 Unicode 以便用于 intranet 地址。 此设置对于正确的 DNS 名称解析十分重要。 请注意，无需为 Windows 8 和更新版本配置此设置。  
  
> [!WARNING]
>  您应该永远不会使用 Punycode 对地址进行硬代码。 WCF 将会基于您应用的配置设置为您转换它。  
  
> [!WARNING]
>  将 Unicode 字符添加到 applicationHost.exe.config 时，使用 UTF-8 编码保存文件。  
  
## <a name="see-also"></a>请参阅  
 [System.Uri](http://msdn.microsoft.com/library/system.uri.aspx)
