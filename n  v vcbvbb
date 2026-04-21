addEventListener("fetch", event => {
  event.respondWith(handleRequest(event.request));
});

async function handleRequest(request) {
  const url = new URL(request.url);

  url.hostname = "https://archive.org/.com"; 

  const newRequest = new Request(url.toString(), request);
  newRequest.headers.set("Referer", "https://blocked-site.com");
  newRequest.headers.set("Origin", "https://blocked-site.com");

  return fetch(newRequest);
}
