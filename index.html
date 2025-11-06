<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NtQueryInformationProcess Documentation</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/styles/vs2015.min.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/highlight.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/languages/cpp.min.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #1e1e1e;
            color: #ffffff;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            padding: 40px 20px;
        }

        .container {
            max-width: 1100px;
            margin: 0 auto;
        }

        h1 {
            color: #4ec9b0;
            font-size: 2.5em;
            margin-bottom: 40px;
            border-bottom: 2px solid #404040;
            padding-bottom: 15px;
        }

        h2 {
            color: #569cd6;
            font-size: 1.8em;
            margin-top: 50px;
            margin-bottom: 20px;
        }

        h3 {
            color: #4ec9b0;
            font-size: 1.3em;
            margin-top: 30px;
            margin-bottom: 15px;
        }

        .explanation {
            background-color: #2d2d2d;
            padding: 25px;
            border-radius: 8px;
            margin-bottom: 20px;
            border-left: 4px solid #569cd6;
        }

        .explanation p {
            margin-bottom: 15px;
            font-size: 1.05em;
        }

        .explanation p:last-child {
            margin-bottom: 0;
        }

        .code-section {
            margin-bottom: 30px;
        }

        .code-label {
            color: #9cdcfe;
            font-size: 1.1em;
            font-weight: 600;
            margin-bottom: 10px;
            display: block;
        }

        pre {
            background-color: #1e1e1e;
            border: 1px solid #404040;
            border-radius: 8px;
            padding: 20px;
            overflow-x: auto;
            margin-bottom: 30px;
        }

        code {
            font-family: 'Consolas', 'Courier New', monospace;
            font-size: 0.95em;
        }

        .inline-code {
            background-color: #3c3c3c;
            color: #ce9178;
            padding: 2px 6px;
            border-radius: 3px;
            font-family: 'Consolas', 'Courier New', monospace;
        }

        a {
            color: #569cd6;
            text-decoration: none;
        }

        a:hover {
            text-decoration: underline;
        }

        .note {
            background-color: #2d4a2d;
            border-left: 4px solid #4ec9b0;
            padding: 15px;
            margin: 20px 0;
            border-radius: 4px;
        }

        .warning {
            background-color: #4a3d2d;
            border-left: 4px solid #ce9178;
            padding: 15px;
            margin: 20px 0;
            border-radius: 4px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>NtQueryInformationProcess Documentation</h1>

        <h2>1.3. NtQueryInformationProcess()</h2>

        <div class="explanation">
            <p>The function <span class="inline-code">ntdll!NtQueryInformationProcess()</span> can retrieve a different kind of information from a process. It accepts a <span class="inline-code">ProcessInformationClass</span> parameter which specifies the information you want to get and defines the output type of the <span class="inline-code">ProcessInformation</span> parameter.</p>
        </div>

        <h3>1.3.1. ProcessDebugPort</h3>

        <div class="explanation">
            <p>It is possible to retrieve the port number of the debugger for the process using the <span class="inline-code">ntdll!NtQueryInformationProcess()</span>. There is a documented class <span class="inline-code">ProcessDebugPort</span>, which retrieves a DWORD value equal to <span class="inline-code">0xFFFFFFFF</span> (decimal -1) if the process is being debugged.</p>
        </div>

        <div class="code-section">
            <span class="code-label">C/C++ Code</span>
            <pre><code class="language-cpp">typedef NTSTATUS (NTAPI *TNtQueryInformationProcess)(
    IN HANDLE               ProcessHandle,
    IN PROCESSINFOCLASS     ProcessInformationClass,
    OUT PVOID               ProcessInformation,
    IN ULONG                ProcessInformationLength,
    OUT PULONG              ReturnLength
);

HMODULE hNtdll = LoadLibraryA("ntdll.dll");
if (hNtdll)
{
    auto pfnNtQueryInformationProcess = (TNtQueryInformationProcess)GetProcAddress(
        hNtdll, "NtQueryInformationProcess");
    
    if (pfnNtQueryInformationProcess)
    {
        DWORD dwDebugPort = 0;
        NTSTATUS status = pfnNtQueryInformationProcess(
            GetCurrentProcess(),
            ProcessDebugPort,
            &dwDebugPort,
            sizeof(DWORD),
            NULL);
        
        if (status == 0 && dwDebugPort == 0xFFFFFFFF)
        {
            printf("Debugger detected!\n");
        }
    }
    FreeLibrary(hNtdll);
}</code></pre>
        </div>

        <h3>1.3.2. ProcessDebugObjectHandle</h3>

        <div class="explanation">
            <p>Another useful information class is <span class="inline-code">ProcessDebugObjectHandle</span>. When a debugger is attached to a process, a debug object is created and associated with the process. This method attempts to retrieve a handle to that debug object.</p>
            <p>If the function succeeds and returns a valid handle, it indicates that the process is being debugged. The handle should be closed using <span class="inline-code">CloseHandle()</span> after use.</p>
        </div>

        <div class="code-section">
            <span class="code-label">C/C++ Code</span>
            <pre><code class="language-cpp">HANDLE hDebugObject = NULL;
NTSTATUS status = pfnNtQueryInformationProcess(
    GetCurrentProcess(),
    ProcessDebugObjectHandle,
    &hDebugObject,
    sizeof(HANDLE),
    NULL);

if (status == 0 && hDebugObject != NULL)
{
    printf("Debugger detected via debug object!\n");
    CloseHandle(hDebugObject);
}</code></pre>
        </div>

        <div class="note">
            <strong>Note:</strong> The ProcessDebugObjectHandle method is available on Windows XP and later versions. It provides a more reliable detection method compared to ProcessDebugPort.
        </div>

        <h3>1.3.3. ProcessDebugFlags</h3>

        <div class="explanation">
            <p>The <span class="inline-code">ProcessDebugFlags</span> information class returns the inverse of the NoDebugInherit flag. When a process is being debugged, this flag is set to 0. When not being debugged, it returns a non-zero value (typically 1).</p>
            <p>This method is particularly useful because it's harder for anti-anti-debugging tools to intercept, as it's less commonly monitored than other detection methods.</p>
        </div>

        <div class="code-section">
            <span class="code-label">C/C++ Code</span>
            <pre><code class="language-cpp">DWORD dwDebugFlags = 0;
NTSTATUS status = pfnNtQueryInformationProcess(
    GetCurrentProcess(),
    ProcessDebugFlags,
    &dwDebugFlags,
    sizeof(DWORD),
    NULL);

if (status == 0 && dwDebugFlags == 0)
{
    printf("Debugger detected via debug flags!\n");
}</code></pre>
        </div>

        <div class="warning">
            <strong>Warning:</strong> These anti-debugging techniques can be bypassed by sophisticated debuggers and should not be relied upon as the sole protection mechanism. Always use multiple detection methods in combination.
        </div>

    </div>

    <script>
        hljs.highlightAll();
    </script>
</body>
</html>
