# wpfbrowserscripting
Demo of scripting using WPF browser control

Did you know that WPF Browser Control provides a way via COM to execute C# code?

Check out:
WebBrowser.ObjectForScripting

For documentation see:
https://msdn.microsoft.com/en-us/library/system.windows.forms.webbrowser.objectforscripting(v=vs.110).aspx

Snippet

      namespace WpfBrowserScripting
      {
          [ComVisible(true)]
          public class ScriptingExample
          {
              public void Message(string message)
              {
                  MessageBox.Show("From C#: " + message);
              }
          }
      }

...

    Browser.ObjectForScripting = new ScriptingExample();

Then in your HTML

      <form>
          <button type="button" onclick="script: window.external.Message('This text came from web page');">Send some text to C#</button>
      </form>
