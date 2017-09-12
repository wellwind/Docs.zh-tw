# <a name="response-compression-sample-application-aspnet-core-2x"></a><span data-ttu-id="8e668-101">回應壓縮範例應用程式 (ASP.NET Core 2.x)</span><span class="sxs-lookup"><span data-stu-id="8e668-101">Response compression sample application (ASP.NET Core 2.x)</span></span>

<span data-ttu-id="8e668-102">此範例說明如何使用 ASP.NET Core 2.x 回應壓縮來壓縮的 HTTP 回應的中介軟體。</span><span class="sxs-lookup"><span data-stu-id="8e668-102">This sample illustrates the use of ASP.NET Core 2.x Response Compression Middleware to compress HTTP responses for.</span></span> <span data-ttu-id="8e668-103">此範例示範 Gzip 和自訂壓縮提供者的文字和影像的回應，並示範如何加入壓縮的 MIME 類型。</span><span class="sxs-lookup"><span data-stu-id="8e668-103">The sample demonstrates Gzip and custom compression providers for text and image responses and shows how to add a MIME type for compression.</span></span> <span data-ttu-id="8e668-104">如需 ASP.NET Core 1.x 範例中，請參閱[回應壓縮範例應用程式 (ASP.NET Core 1.x)](https://github.com/aspnet/Docs/tree/master/aspnetcore/performance/response-compression/samples/1.x)。</span><span class="sxs-lookup"><span data-stu-id="8e668-104">For the ASP.NET Core 1.x sample, see [Response compression sample application (ASP.NET Core 1.x)](https://github.com/aspnet/Docs/tree/master/aspnetcore/performance/response-compression/samples/1.x).</span></span>

## <a name="examples-in-this-sample"></a><span data-ttu-id="8e668-105">在此範例中的範例</span><span class="sxs-lookup"><span data-stu-id="8e668-105">Examples in this sample</span></span>
* `GzipCompressionProvider`
  * `text/plain`
    * <span data-ttu-id="8e668-106">**/**-Lorem Ipsum 檔案回應的文字在 2,044 將經過壓縮以 927 位元組的位元組</span><span class="sxs-lookup"><span data-stu-id="8e668-106">**/** - Lorem Ipsum text file response at 2,044 bytes that will compress to 927 bytes</span></span>
    * <span data-ttu-id="8e668-107">**/testfile1kb.txt** -回應在 1,033 將經過壓縮以 47 位元組的位元組的文字檔案</span><span class="sxs-lookup"><span data-stu-id="8e668-107">**/testfile1kb.txt** - Text file response at 1,033 bytes that will compress to 47 bytes</span></span>
    * <span data-ttu-id="8e668-108">**緩慢/** -1 秒的間隔為單一字元發出的回應</span><span class="sxs-lookup"><span data-stu-id="8e668-108">**/trickle** - Response issued as single characters at 1 second intervals</span></span> 
  * `image/svg+xml`
    * <span data-ttu-id="8e668-109">**/banner.svg** -A 向量圖形 (SVG) 映像回應在 9,707 將經過壓縮以 4,459 位元組的位元組</span><span class="sxs-lookup"><span data-stu-id="8e668-109">**/banner.svg** - A Scalable Vector Graphics (SVG) image response at 9,707 bytes that will compress to 4,459 bytes</span></span>
* `CustomCompressionProvider`<br><span data-ttu-id="8e668-110">示範如何實作與中介軟體搭配使用的自訂壓縮提供者</span><span class="sxs-lookup"><span data-stu-id="8e668-110">Shows how to implement a custom compression provider for use with the middleware</span></span>

<span data-ttu-id="8e668-111">當要求包含`Accept-Encoding`標頭和回應的壓縮作業成功中, 介軟體會自動將加入`Vary: Accept-Encoding`標頭至回應。</span><span class="sxs-lookup"><span data-stu-id="8e668-111">When the request includes the `Accept-Encoding` header and response compression is successful, the middleware automatically adds a `Vary: Accept-Encoding` header to the response.</span></span> <span data-ttu-id="8e668-112">`Vary`標頭指示維護多份依據替代值的回應的快取`Accept-Encoding`，因此同時壓縮 (gzip) 和未壓縮的版本會儲存在快取的系統，可以接受壓縮或未壓縮的回應。</span><span class="sxs-lookup"><span data-stu-id="8e668-112">The `Vary` header instructs caches to maintain multiple copies of the response based on alternative values of `Accept-Encoding`, so both a compressed (gzip) and uncompressed version are stored in caches for systems that can either accept the compressed or the uncompressed response.</span></span>

## <a name="using-the-sample"></a><span data-ttu-id="8e668-113">使用範例</span><span class="sxs-lookup"><span data-stu-id="8e668-113">Using the sample</span></span>
1. <span data-ttu-id="8e668-114">請要求使用[Fiddler](http://www.telerik.com/fiddler)， [firebug 這類](http://getfirebug.com/)，或[郵差](https://www.getpostman.com/)應用程式不含`Accept-Encoding`標頭和附註的回應裝載，回應大小和回應標頭。</span><span class="sxs-lookup"><span data-stu-id="8e668-114">Make a request using [Fiddler](http://www.telerik.com/fiddler), [Firebug](http://getfirebug.com/), or [Postman](https://www.getpostman.com/) to the application without an `Accept-Encoding` header and note the response payload, response size, and response headers.</span></span>
2. <span data-ttu-id="8e668-115">新增`Accept-Encoding: gzip`標頭，並記下壓縮的回應的大小和回應標頭。</span><span class="sxs-lookup"><span data-stu-id="8e668-115">Add an `Accept-Encoding: gzip` header and note the compressed response size and response headers.</span></span> <span data-ttu-id="8e668-116">回應大小會卸除，而`Content-Encoding: gzip`回應標頭會包含由中介軟體。</span><span class="sxs-lookup"><span data-stu-id="8e668-116">The response size drops, and the `Content-Encoding: gzip` response header is included by the middleware.</span></span> <span data-ttu-id="8e668-117">當您查看回應內文的 Lorem Ipsum 或**testfile1kb.txt**回應，您會看到文字為壓縮，無法讀取。</span><span class="sxs-lookup"><span data-stu-id="8e668-117">When you look at the response body for the Lorem Ipsum or **testfile1kb.txt** response, you see that the text is compressed and unreadable.</span></span>
3. <span data-ttu-id="8e668-118">新增`Accept-Encoding: mycustomcompression`標頭，並記下回應標頭。</span><span class="sxs-lookup"><span data-stu-id="8e668-118">Add an `Accept-Encoding: mycustomcompression` header and note the response headers.</span></span> <span data-ttu-id="8e668-119">`CustomCompressionProvider`是實際上不會壓縮回應的空白實作，但是您可以建立自訂的壓縮資料流包裝函式`CreateStream()`方法。</span><span class="sxs-lookup"><span data-stu-id="8e668-119">The `CustomCompressionProvider` is an empty implementation that doesn't actually compress the response, but you can create a custom compression stream wrapper for the `CreateStream()` method.</span></span>