# typesense-instantsearch-demo (without NPM or YARN)

This is a demo that shows you a quick search interface that was built with [typesense-instantsearch-adapter](https://github.com/typesense/typesense-instantsearch-adapter).

This is very similar to [typesense-instantsearch-demo](https://github.com/typesense/typesense-instantsearch-demo), but doesn't use NPM or YARN, and instead uses `script` tags in HTML.

## Get started

To run this project locally:

### 1️⃣ Start Typesense Server

```shell
docker run -i -p 8108:8108 -v/tmp/typesense-server-data-1c/:/data typesense/typesense:0.23.1 --data-dir /data --api-key=xyz --listen-port 8108 --enable-cors
```

[Here](https://typesense.org/docs/guide/install-typesense.html) are more ways to install and start Typesense.

### 2️⃣ Index Sample Dataset

From the root of this repository run the following `curl` commands:

```shell
curl "http://localhost:8108/collections" \
      -X POST \
      -H "Content-Type: application/json" \
      -H "X-TYPESENSE-API-KEY: xyz" \
      -d '{
            "name": "books",
            "fields": [
              {
                "name": "title",
                "type": "string"
              },
              {
                "name": "authors",
                "type": "string[]",
                "facet": true
              },
              {
                "name": "publication_year",
                "type": "int32",
                "facet": true
              },
              {
                "name": "ratings_count",
                "type": "int32"
              },
              {
                "name": "average_rating",
                "type": "float",
                "facet": true
              }
            ],
            "default_sorting_field": "ratings_count"
          }'
```

```shell
curl "http://localhost:8108/collections/books/documents/import?action=create" \
      -X POST \
      -H "X-TYPESENSE-API-KEY: xyz" \
      --data-binary @./data/books.jsonl
```

### 3️⃣ Open `index.html`

Now open the `index.html` file in the root of this repo in a web browser, to see the search UI.