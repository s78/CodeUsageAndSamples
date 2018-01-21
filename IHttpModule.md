###### System.Web.IHttpModule
### IHttpModule

Http Module Template
``` csharp
public class CustomModule : IHttpModule
{
    public void Init(HttpApplication app)
    {
        app.BeginRequest += App_BeginRequest;
        app.EndRequest += App_EndRequest;
    }

    private void App_BeginRequest(object source, EventArgs e)
    {
        var app = (HttpApplication)source;
    }

    private void App_EndRequest(object source, EventArgs e)
    {
        var app = (HttpApplication)source;
    }

    public void Dispose() { }
}
```