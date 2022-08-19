<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <meta name="theme-color" content="#000000">

    <link rel="manifest" href="./manifest.webmanifest">
    <link rel="shortcut icon" href="./favicon.png">

    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/instantsearch.css@7/themes/algolia-min.css">
    <link rel="stylesheet" href="index.css">

    <title>Typesense InstantSearch.js Demo</title>
</head>

<body>
<header class="header">
    <h1 class="header-title">
        <a href="/">Instant Search Demo</a>
    </h1>
    <p class="header-subtitle">
        using
        <a href="https://github.com/algolia/instantsearch.js">
            Typesense + InstantSearch.js
        </a>
    </p>
</header>

<div class="container">
    <div class="search-panel">
        <div class="search-panel__results">
            <div id="searchbox"></div>
            <div id="hits"></div>
        </div>
    </div>

    <div id="pagination"></div>
</div>

<script src="https://cdn.jsdelivr.net/npm/instantsearch.js@4.44.0"></script>
<script src="https://cdn.jsdelivr.net/npm/typesense-instantsearch-adapter@2/dist/typesense-instantsearch-adapter.min.js"></script>

<script>
    const typesenseInstantsearchAdapter = new TypesenseInstantSearchAdapter({
        server: {
            apiKey: 'xyz', // Be sure to use an API key that only allows searches, in production
            nodes: [
                {
                    host: 'localhost',
                    port: '8108',
                    protocol: 'http',
                },
            ],
        },
        // The following parameters are directly passed to Typesense's search API endpoint.
        //  So you can pass any parameters supported by the search endpoint below.
        //  queryBy is required.
        //  filterBy is managed and overridden by InstantSearch.js. To set it, you want to use one of the filter widgets like refinementList or use the `configure` widget.
        additionalSearchParameters: {
            queryBy: 'title,authors',
        },
    });
    const searchClient = typesenseInstantsearchAdapter.searchClient;

    const search = instantsearch({
        searchClient,
        indexName: 'books',
    });

    search.addWidgets([
        instantsearch.widgets.searchBox({
            container: '#searchbox',
        }),
        instantsearch.widgets.configure({
            hitsPerPage: 8,
        }),
        instantsearch.widgets.hits({
            container: '#hits',
            templates: {
                item(item) {
                    return `
                        <div>
                          <img src="${item.image_url}" alt="${item.name}" height="100" />
                          <div class="hit-name">
                            ${item._highlightResult.title.value}
                          </div>
                          <div class="hit-authors">
                          ${item._highlightResult.authors.map((a) => a.value).join(', ')}
                          </div>
                          <div class="hit-publication-year">${item.publication_year}</div>
                          <div class="hit-rating">${item.average_rating}/5 rating</div>
                        </div>
                      `;
                },
            },
        }),
        instantsearch.widgets.pagination({
            container: '#pagination',
        }),
    ]);

    search.start();
</script>
</body>
</html>
