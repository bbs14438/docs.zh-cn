---
title: '&lt;ws2007HttpBinding&gt; 的 &lt;transport&gt;'
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 3be9d4e64e63b32156cb64257f5bed8230cee3aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="lttransportgt-of-ltws2007httpbindinggt"></a>&lt;ws2007HttpBinding&gt; 的 &lt;transport&gt;
定义 HTTP 传输的身份验证设置。  
  
 \<system.serviceModel>  
\<绑定 >  
\<ws2007HttpBinding>  
\<绑定 >  
\<安全 >  
\<transport>  
  
## <a name="syntax"></a>语法  
  
```  
transport clientCredentialType =   
       "Basic/Certificate/Digest/None/Ntlm/Windows"  
       proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
       realm="string"   
```  
  
## <a name="type"></a>类型  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`clientCredentialType`|指定用于向服务证明客户端身份的凭据。 此属性的类型为 <xref:System.ServiceModel.HttpClientCredentialType>。|  
|`proxyCredentialType`|指定用于向域代理证明客户端身份的凭据。 此属性的类型为 <xref:System.ServiceModel.HttpProxyCredentialType>。|  
|`realm`|摘要式或基本身份验证的身份验证领域。 默认值为一个空字符串。<br /><br /> 身份验证领域至少指定执行身份验证的主机的名称。 它还可以指定具有访问权限的用户集合。 用户可以查询身份验证领域，以确定多个可能的用户名和密码中哪一个可以使用。|  
  
## <a name="clientcredentialtype-attribute"></a>clientCredentialType 属性  
  
|值|描述|  
|-----------|-----------------|  
|无|禁用安全性。|  
|Basic|使用基本身份验证。|  
|摘要|使用摘要式身份验证。|  
|Ntlm|对 Windows 域使用 NTLM 身份验证作为回退。|  
|Windows|使用集成 Windows 身份验证。|  
|证书|使用 X.509 证书对客户端进行身份验证。|  
  
## <a name="proxycredentialtype-attribute"></a>proxyCredentialType 属性  
  
|值|描述|  
|-----------|-----------------|  
|无|禁用安全性。|  
|Basic|使用基本身份验证。|  
|摘要|使用摘要式身份验证。|  
|Ntlm|对 Windows 域使用 NTLM 作为回退。|  
|Windows|使用集成 Windows 身份验证。|  
|证书|使用 X.509 证书对客户端进行身份验证。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|表示的安全功能[ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)元素。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>  
 [保护服务和客户端的安全](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [绑定](../../../../../docs/framework/wcf/bindings.md)  
 [配置系统提供的绑定](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [使用绑定来配置 Windows Communication Foundation 服务和客户端](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<绑定 >](../../../../../docs/framework/misc/binding.md)
