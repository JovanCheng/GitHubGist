```html
<%@ Page Language="C#" %>
<%@ Import Namespace = "EX_Extension" %>

<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">

<script runat="server">

</script>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
</head>
<body>
    <form id="form1" runat="server">
    <div><table>
<%
    Response.Write("<tr><td>Session.Timeout: " + Session.Timeout + " minute(s) </td></tr>");
    Response.Write("<tr><td>Session.SessionID: " + Session.SessionID + " </td></tr>");
    Response.Write("<tr><td>There are " + Session.Contents.Count + " Session variables</td></tr>");

 /*   //var strName, iloop;
   foreach (object strName in Session.Contents)
     if (strName is System.Array) 
     {
        for (int iLoop = LBound(Session[strName]) to UBound(Session(strName)))
       {
          Response.Write(strName + "(" + iLoop + ") - " + Session[strName][iLoop] + "<br />";
       }
     else
       {
        Response.Write(strName = " - " + Session.Contents[strName] + "<br />";
       }
       //next
    }
  */

    foreach (string key in Session.Keys)
    {
        Response.Write("<tr><td>" +key + "</td><td>" + Session[key].intoNoNullTrim() + "</td></tr>");
    }

%>

  </table>  
    </div>
    </form>
</body>
</html>

```
