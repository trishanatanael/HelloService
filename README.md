# HelloService WSDL
http://localhost:8080/?wsdl
Tutorial: https://www.youtube.com/watch?v=UcmD1SfIayM&t=1219s

<wsdl:definitions xmlns:wsdl="http://schemas.xmlsoap.org/wsdl/" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soapenc="http://schemas.xmlsoap.org/soap/encoding/" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd" xmlns:soap="http://schemas.xmlsoap.org/wsdl/soap/" xmlns:soap12="http://schemas.xmlsoap.org/wsdl/soap12/" xmlns:tns="http://tempuri.org/" xmlns:wsa="http://schemas.xmlsoap.org/ws/2004/08/addressing" xmlns:wsx="http://schemas.xmlsoap.org/ws/2004/09/mex" xmlns:wsap="http://schemas.xmlsoap.org/ws/2004/08/addressing/policy" xmlns:wsaw="http://www.w3.org/2006/05/addressing/wsdl" xmlns:msc="http://schemas.microsoft.com/ws/2005/12/wsdl/contract" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wsa10="http://www.w3.org/2005/08/addressing" xmlns:wsam="http://www.w3.org/2007/05/addressing/metadata" name="HelloService" targetNamespace="http://tempuri.org/">
<wsdl:types>
<xsd:schema targetNamespace="http://tempuri.org/Imports">
<xsd:import schemaLocation="http://localhost:8080/?xsd=xsd0" namespace="http://tempuri.org/"/>
<xsd:import schemaLocation="http://localhost:8080/?xsd=xsd1" namespace="http://schemas.microsoft.com/2003/10/Serialization/"/>
</xsd:schema>
</wsdl:types>
<wsdl:message name="IHelloService_GetMessage_InputMessage">
<wsdl:part name="parameters" element="tns:GetMessage"/>
</wsdl:message>
<wsdl:message name="IHelloService_GetMessage_OutputMessage">
<wsdl:part name="parameters" element="tns:GetMessageResponse"/>
</wsdl:message>
<wsdl:portType name="IHelloService">
<wsdl:operation name="GetMessage">
<wsdl:input wsaw:Action="http://tempuri.org/IHelloService/GetMessage" message="tns:IHelloService_GetMessage_InputMessage"/>
<wsdl:output wsaw:Action="http://tempuri.org/IHelloService/GetMessageResponse" message="tns:IHelloService_GetMessage_OutputMessage"/>
</wsdl:operation>
</wsdl:portType>
<wsdl:binding name="BasicHttpBinding_IHelloService" type="tns:IHelloService">
<soap:binding transport="http://schemas.xmlsoap.org/soap/http"/>
<wsdl:operation name="GetMessage">
<soap:operation soapAction="http://tempuri.org/IHelloService/GetMessage" style="document"/>
<wsdl:input>
<soap:body use="literal"/>
</wsdl:input>
<wsdl:output>
<soap:body use="literal"/>
</wsdl:output>
</wsdl:operation>
</wsdl:binding>
<wsdl:service name="HelloService">
<wsdl:port name="BasicHttpBinding_IHelloService" binding="tns:BasicHttpBinding_IHelloService">
<soap:address location="http://localhost:8080/HelloService"/>
</wsdl:port>
</wsdl:service>
</wsdl:definitions>
