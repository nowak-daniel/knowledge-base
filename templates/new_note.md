---
tags:
datum: <% tp.date.now("YYYY-MM-DD") %>
---
<%
await tp.file.rename(tp.date.now("YYYYMMDD") + "_")
%>
