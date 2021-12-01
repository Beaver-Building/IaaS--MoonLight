Chromium DevTools + Chromium URLs

# Chromium Build-in Tools

## DevTools Overview

#### DeveloperToolsAvailability
-   DeveloperToolsAllowed (1) = Allow using the developer tools
    
-   DeveloperToolsDisallowed (2) = Don't allow using the developer tools
### Console
View (Filter) messages  **Show Console Sidebar** ![Show Console Sidebar](https://wd.imgix.net/image/admin/WCuENTqHgjAR2Be3Hdqq.png?auto=format).
-   Making sure that code is executing in the right order.
-   Inspecting the values of variables at a certain moment in time.
Run JavaScript

### Storage
http cache/cookie/session storage/local storage

### Network
Analyze/Sort/Filter network requests
-   **Status**. The HTTP response code.
    
-   **Type**. The resource type.
    
-   **Initiator**. What caused a resource to be requested. Clicking a link in the Initiator column takes you to the source code that caused the request.
    
-   **Time**. How long the request took.
    
-   **Waterfall**. A graphical representation of the different stages of the request. Hover over a Waterfall to see a breakdown.
![[Pasted image 20211101234446.png]]

Change loading behavior

### Net Export
ref: https://zhuanlan.zhihu.com/p/266622278

net_log generation:
1. --log-net-log subfix
2. chrome://net-export
3. https://netlog-viewer.appspot.com/#import

Explanation
filter type: url_request
event: https://source.chromium.org/chromium/chromium/src/+/master:net/log/net_log_event_type_list.h
t: chrome start time
st: session start time
dt: duration time

```text
10: URL_REQUEST
https://clientservices.googleapis.com/chrome-variations/seed?osname=win&channel=stable&milestone=86
Start Time: 2020-10-19 12:27:35.822

//每个URL_REQUEST的根节点都是REQUEST_ALIVE
t=100 [st=  0] +REQUEST_ALIVE  [dt=512]
                --> priority = "IDLE"
//priority的取值有5种，从定义可以看到
//enum RequestPriority {
//  THROTTLED = 0,  // Used to signal that resources
//                  // should be reserved for following
//                  // requests (i.e. that higher priority
//                  // following requests are expected).
//  MINIMUM_PRIORITY = THROTTLED,
//  IDLE = 1,  // Default "as resources available" level.
//  LOWEST = 2,
//  DEFAULT_PRIORITY = LOWEST,
//  LOW = 3,
//  MEDIUM = 4,
//  HIGHEST = 5,
//  MAXIMUM_PRIORITY = HIGHEST,
//};
//chrome会根据资源类型决定priority，例如js，css显然需要高优先级，img需要低优先级，普通页面
//的优先级在两者之间

                --> traffic_annotation = 115188287
//traffic_annotation这个数字是一串string的哈希值，这串string是用来解释说明这个
//network traffic的，traffic_annotation这个字段很少会用到

                --> url = "https://clientservices.googleapis.com/chrome-variations/seed?osname=win&channel=stable&milestone=86"
t=100 [st=  0]    NETWORK_DELEGATE_BEFORE_URL_REQUEST  [dt=0]
t=100 [st=  0]   +URL_REQUEST_START_JOB  [dt=512]
//每个request都会有一个URL_REQUEST_START_JOB，在chrome代码中对应着URLRequestJob，这是一个
//基类，它最重要，最常用的子类是URLRequestHttpJob
                  --> initiator = "not an origin"
//initiator是这个request的发起者，有点像Referer，但不完全是，并且它只是个scheme+host的部分，
//列举几个它的取值就能感受到它的意义，例如：chrome://newtab, chrome://new-tab-page,
//https://www.zhihu.com, https://ogs.google.com等等
                  --> load_flags = 832 (DO_NOT_SAVE_COOKIES | DO_NOT_SEND_AUTH_DATA | DO_NOT_SEND_COOKIES)
//load_flags是非常非常重要的一个属性，它的所有取值都定义在net/base/load_flags_list.h中，
//例如这里的DO_NOT_SAVE_COOKIES代表不要存cookie，也就是忽略response里的set-cookie
//DO_NOT_SEND_AUTH_DATA代表不要发送name，password这样的authentication数据，这个字段在最新的
//chromium中已被删除
//DO_NOT_SEND_COOKIES代表不要发送cookie，也就是request中没有任何cookie内容
                  --> method = "GET"

//network_isolation_key包含2个scheme+host的域名，第一个是top_frame_site，第二个是发起这个request的frame
                  --> network_isolation_key = "null null"

//privacy_mode用来控制发送request时是否带cookie
                  --> privacy_mode = "enabled"

//site_for_cookies存着对于当前这个request，它的first party origin是什么，用在cookie访问控制上
                  --> site_for_cookies = "SiteForCookies: {scheme=; registrable_domain=; schemefully_same=false}"
                  --> url = "https://clientservices.googleapis.com/chrome-variations/seed?osname=win&channel=stable&milestone=86"
t=100 [st=  0]      NETWORK_DELEGATE_BEFORE_START_TRANSACTION  [dt=0]
//HTTP_STREAM_REQUEST代表建立socket连接的过程
t=103 [st=  3]     +HTTP_STREAM_REQUEST  [dt=337]
t=103 [st=  3]        HTTP_STREAM_JOB_CONTROLLER_BOUND
                      --> source_dependency = 11 (HTTP_STREAM_JOB_CONTROLLER)
t=440 [st=340]        HTTP_STREAM_REQUEST_BOUND_TO_JOB
                      --> source_dependency = 12 (HTTP_STREAM_JOB)
t=440 [st=340]     -HTTP_STREAM_REQUEST

//HTTP_TRANSACTION_SEND_REQUEST是发送request header的过程
t=440 [st=340]     +HTTP_TRANSACTION_SEND_REQUEST  [dt=0]
t=440 [st=340]        HTTP_TRANSACTION_HTTP2_SEND_REQUEST_HEADERS
//这里显然是发送HTTP2的request header
                      --> :method: GET
                          :authority: clientservices.googleapis.com
                          :scheme: https
                          :path: /chrome-variations/seed?osname=win&channel=stable&milestone=86
                          if-none-match: d98f79ee75dca090f72faa358fa28c4a885c49fc
                          a-im: x-bm,gzip
                          sec-fetch-site: none
                          sec-fetch-mode: no-cors
                          sec-fetch-dest: empty
                          user-agent: Mozilla/5.0 (Windows NT 6.3; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.75 Safari/537.36
                          accept-encoding: gzip, deflate, br
t=440 [st=340]     -HTTP_TRANSACTION_SEND_REQUEST
//HTTP_TRANSACTION_READ_HEADERS是收到了response header
t=440 [st=340]     +HTTP_TRANSACTION_READ_HEADERS  [dt=172]
//HTTP2_STREAM_UPDATE_SEND_WINDOW是socket stream发送byte的window size调整，是http之下的socket

t=479 [st=379]        HTTP2_STREAM_UPDATE_SEND_WINDOW
                      --> delta = 983041
                      --> stream_id = 1
                      --> window_size = 1048576
//下面是response header内容
t=612 [st=512]        HTTP_TRANSACTION_READ_RESPONSE_HEADERS
                      --> HTTP/1.1 304
                          status: 304
                          x-content-type-options: nosniff
                          x-frame-options: SAMEORIGIN
                          x-xss-protection: 0
                          date: Mon, 19 Oct 2020 04:27:35 GMT
                          alt-svc: h3-Q050=":443"; ma=2592000,h3-29=":443"; ma=2592000,h3-27=":443"; ma=2592000,h3-T051=":443"; ma=2592000,h3-T050=":443"; ma=2592000,h3-Q046=":443"; ma=2592000,h3-Q043=":443"; ma=2592000,quic=":443"; ma=2592000; v="46,43"
t=612 [st=512]     -HTTP_TRANSACTION_READ_HEADERS
t=612 [st=512]      NETWORK_DELEGATE_HEADERS_RECEIVED  [dt=0]
t=612 [st=512]   -URL_REQUEST_START_JOB
t=612 [st=512]    URL_REQUEST_DELEGATE_RESPONSE_STARTED  [dt=0]
//HTTP_TRANSACTION_READ_BODY是读取response body的过程，这个response太短，所以只显示了一句
t=612 [st=512]    HTTP_TRANSACTION_READ_BODY  [dt=0]
t=612 [st=512] -REQUEST_ALIVE
```

### Javascript
Fetch/XMLHTTPRequest https://zh.javascript.info/network

### Performance
Analyze runtime performance
#### Analyze the results
Once you've got a recording of the page's performance, you can measure how poor the page's performance is, and find the cause(s).

##### Analyze frames per second

The main metric for measuring the performance of any animation is frames per second (FPS). Users are happy when animations run at 60 FPS.

1.  Look at the **FPS** chart. Whenever you see a red bar above **FPS**, it means that the framerate dropped so low that it's probably harming the user experience. In general, the higher the green bar, the higher the FPS.
    
    ![The FPS chart](https://wd.imgix.net/image/admin/rLbUyQ0Y0p6xIiwy85SK.svg)
    
    **Figure 5**: The FPS chart, outlined in blue
    
2.  Below the **FPS** chart you see the **CPU** chart. The colors in the **CPU** chart correspond to the colors in the **Summary** tab, at the bottom of the Performance panel. The fact that the **CPU** chart is full of color means that the CPU was maxed out during the recording. Whenever you see the CPU maxed out for long periods, it's a cue to find ways to do less work.
    
    ![The CPU chart and Summary tab](https://wd.imgix.net/image/admin/XFtPfdKzTPBXeQC9g9OC.svg)
    
    **Figure 6**: The CPU chart and Summary tab, outlined in blue
    
3.  Hover your mouse over the **FPS**, **CPU**, or **NET** charts. DevTools shows a screenshot of the page at that point in time. Move your mouse left and right to replay the recording. This is called scrubbing, and it's useful for manually analyzing the progression of animations.
    
    ![Viewing a screenshot](https://wd.imgix.net/image/admin/HwxH2YN7r7EbH6X7O9nD.png?auto=format)
    
    **Figure 7**: Viewing a screenshot of the page around the 2000ms mark of the recording
    


### Memory
ref: https://web.stanford.edu/class/cs101/bits-bytes.html
ref: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Memory_Management

native memory + JS heap memory of the page + JS heap memory of all dedicated workers started by the page
#### Memory buffer
The **`ArrayBuffer`** object is used to represent a generic, fixed-length raw binary data buffer.

![Memory buffer](https://wd.imgix.net/image/dPDCek3EhZgLQPGtEG3y0fTn4v82/4dzzRu6TRCB70fmMXjIS.jpg?auto=format)

1.  From the left, the **address** is displayed in hex format.
2.  The **memory** is also shown in hex format, each byte separated by a space. The currently selected byte is highlighted. You can click on the byte or navigate with keyboard (left, right, up, down).
3.  An **ASCII representation** of the memory is shown on the right side. A highlight shows the corresponding value to the selected bits on the byte. Similar to memory, you can click on the byte or navigate with keyboard (left, right, up, down).
![[Pasted image 20211103103231.png]]

#### Visualize memory leaks with Timeline recordings

You can also use the Timeline panel as another starting point in your investigation. The Timeline panel helps you visualize a page's memory use over time.

1.  Open the **Timeline** panel on DevTools.
2.  Enable the **Memory** checkbox.
3.  [Make a recording](https://developer.chrome.com/docs/devtools/evaluate-performance/reference/#record-runtime).

Tip: It's a good practice to start and end your recording with a forced garbage collection. Click the **collect garbage** button (![force garbage collection button](https://wd.imgix.net/image/admin/Qkf1EfUFRSoRsCEMVHdY.png?auto=format)) while recording to force garbage collection.

To demonstrate Timeline memory recordings, consider the code below:

```js
var x = [];function grow() {  for (var i = 0; i < 10000; i++) {    document.body.appendChild(document.createElement('div'));  }  x.push(new Array(1000000).join('x'));}document.getElementById('grow').addEventListener('click', grow);
```

Every time that the button referenced in the code is pressed, ten thousand `div` nodes are appended to the document body, and a string of one million `x` characters is pushed onto the `x` array. Running this code produces a Timeline recording like the following screenshot:

![simple growth example](https://wd.imgix.net/image/admin/pPcZQbQ6EleigzceZoct.png?auto=format)

First, an explanation of the user interface. The **HEAP** graph in the **Overview** pane (below **NET**) represents the JS heap. Below the **Overview** pane is the **Counter** pane. Here you can see memory usage broken down by JS heap (same as **HEAP** graph in the **Overview** pane), documents, DOM nodes, listeners, and GPU memory. Disabling a checkbox hides it from the graph.

Now, an analysis of the code compared with the screenshot. If you look at the node counter (the green graph) you can see that it matches up cleanly with the code. The node count increases in discrete steps. You can presume that each increase in the node count is a call to `grow()`. The JS heap graph (the blue graph) is not as straightforward. In keeping with best practices, the first dip is actually a forced garbage collection (achieved by pressing the **collect garbage** button). As the recording progresses you can see that the JS heap size spikes. This is natural and expected: the JavaScript code is creating the DOM nodes on every button click and doing a lot of work when it creates the string of one million characters. The key thing here is the fact that the JS heap ends higher than it began (the "beginning" here being the point after the forced garbage collection). In the real world, if you saw this pattern of increasing JS heap size or node size, it would potentially mean a memory leak.

#### Discover detached DOM tree memory leaks with Heap Snapshots

A DOM node can only be garbage collected when there are no references to it from either the page's DOM tree or JavaScript code. A node is said to be "detached" when it's removed from the DOM tree but some JavaScript still references it. Detached DOM nodes are a common cause of memory leaks. This section teaches you how to use DevTools' heap profilers to identify detached nodes.

Here's a simple example of detached DOM nodes.

```js
var detachedTree;function create() {  var ul = document.createElement('ul');  for (var i = 0; i < 10; i++) {    var li = document.createElement('li');    ul.appendChild(li);  }  detachedTree = ul;}document.getElementById('create').addEventListener('click', create);
```

Clicking the button referenced in the code creates a `ul` node with ten `li` children. These nodes are referenced by the code but do not exist in the DOM tree, so they're detached.

Heap snapshots are one way to identify detached nodes. As the name implies, heap snapshots show you how memory is distributed among your page's JS objects and DOM nodes at the point of time of the snapshot.

To create a snapshot, open DevTools and go to the **Profiles** panel, select the **Take Heap Snapshot** radio button, and then press the **Take Snapshot** button.

![take heap snapshot](https://wd.imgix.net/image/admin/cZnWVusrPfoLR9R9edO1.png?auto=format)

The snapshot may take some time to process and load. Once it's finished, select it from the lefthand panel (named **HEAP SNAPSHOTS**).

Type `Detached` in the **Class filter** textbox to search for detached DOM trees.

![filtering for detached nodes](https://wd.imgix.net/image/admin/WXv2Bv8LfZKGQBmgcPbl.png?auto=format)

Expand the carats to investigate a detached tree.

![investigating detached tree](https://wd.imgix.net/image/admin/j2sPLeVjZ5tgbmVhs9Ri.png?auto=format)

Nodes highlighted yellow have direct references to them from the JavaScript code. Nodes highlighted red do not have direct references. They are only alive because they are part of the yellow node's tree. In general, you want to focus on the yellow nodes. Fix your code so that the yellow node isn't alive for longer than it needs to be, and you also get rid of the red nodes that are part of the yellow node's tree.

Click on a yellow node to investigate it further. In the **Objects** pane you can see more information about the code that's referencing it. For example, in the screenshot below you can see that the `detachedTree` variable is referencing the node. To fix this particular memory leak, you would study the code that uses `detachedTree` and ensure that it removes its reference to the node when it's no longer needed.

![investigating a yellow node](https://wd.imgix.net/image/admin/YB6UXZtlZ1eleCZUbUuG.png?auto=format)


-   Window global object (in each iframe). There is a distance field in the heap snapshots which is the number of property references on the shortest retaining path from the window.
-   Document DOM tree consisting of all native DOM nodes reachable by traversing the document. Not all of them may have JS wrappers but if they have the wrappers will be alive while the document is alive.
-   Sometimes objects may be retained by debugger context and DevTools console (e.g. after console evaluation). Create heap snapshots with clear console and no active breakpoints in the debugger.

![[Pasted image 20211103140737.png]]

More Info: 
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures

https://developer.chrome.com/docs/devtools/memory-problems/memory-101/