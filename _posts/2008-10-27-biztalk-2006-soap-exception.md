---
layout: post
title:  Biztalk 2006 - Soap Exception
date: 2008-10-27 13:18:00.000000000 +00:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
excerpt: Multiple Activate Receives and Returning Soap Faults Oddity...
---

#  Biztalk 2006 - Soap Exception
Temos o seguinte cenário:
- Publicação de Orquestração do BizTalk como WebService (Request Response)
- Dentro da Orquestração chamada a Web Service Externo (Request - Response)
<br />
- Admitir <strong>Web Service Externo Offline</strong>

Como retornar à aplicação que invoca WS Orquestração Objecto com Erro de Offline?

De entre algumas formas de retornar, incluindo a forma apresentada na mensagem anterior, prefiro esta abaixo descrita.

Mensagem exemplo a utilizar como msg de resultado abaixo colocada:
Inicio Orquestração, depois de colocar "<em>Shape Receive</em>", construir MSG de Resultado limpa.
Invocar WS Externo dentro de um "<em>Scope</em>", aí criar um "<em>New exception Handler</em>" do tipo "<em>Soap Exception</em>", dentro do "<em>Catch</em>", colcar os dados que se quer na mensagem, assim, quando a "MSG de <em>Response</em>" à orquestração chegar à aplicação, esta terá a justificação do erro. No meu caso o que fiz foi o seguinte:
Coloquei em Status - "NOK"<br />Message - "Erro ao aceder ao WS Externo"
