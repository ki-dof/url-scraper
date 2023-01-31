# url-scraper

Rust crate for scraping URLs from HTML pages.

## Example

```rust
extern crate url_scraper;
use url_scraper::UrlScraper;

#[tokio::main(flavor = "current_thread")]
async fn main() {
    let directory = "https://phoronix.com/";

    let scraper = UrlScraper::new(directory).await.unwrap();
    for (text, url) in scraper.into_iter().await {
        println!("{text}: {url}");
    }
}
```