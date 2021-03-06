---
swagger: "2.0"
x-collection-name: NewsCred
x-complete: 0
info:
  title: News Cred Source Articles
  description: Returns a list of articles provided by the specified source
  version: v1
host: api.newscred.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  category/dashed-name/sources/:
    get:
      summary: Category Sources
      description: Gets a list of sources that write most frequently about the category
        specified by the dashed name
      operationId: getCategoryDashedNameSources
      x-api-path-slug: categorydashednamesources-get
      parameters:
      - in: query
        name: access_key
        description: Unique API access key
      - in: query
        name: from_date
        description: Beginning of date range for which items are searched
      - in: query
        name: media_types
        description: Space delimited list of media types to retreive articles from
      - in: query
        name: offset
        description: Number of items to skip before beginning the result set
      - in: query
        name: pagesize
        description: Number of items to return
      - in: query
        name: sources
        description: List of sources to retrieve items from
      - in: query
        name: source_countries
        description: Search against only sources from the specified countries
      - in: query
        name: source_filter_mode
        description: Enables source_filter_name and indicates filtering type
      - in: query
        name: source_filter_name
        description: Limit items to a predefined list of sources
      - in: query
        name: to_date
        description: End of date range for which items are searched
      responses:
        200:
          description: OK
      tags:
      - News
      - Category
      - Dashed-name
      - Sources
  sources/:
    get:
      summary: Sources
      description: Search sources by name. Returns a list of sources objects
      operationId: getSources
      x-api-path-slug: sources-get
      parameters:
      - in: query
        name: access_key
        description: Unique API access key
      - in: query
        name: autosuggest
        description: If true, partial matches will be returned starting from 3 characters,
          i
      - in: query
        name: licensed
        description: If true, return only licensed sources with fully licensed content
      - in: query
        name: media_types
        description: Limit the media type of the returned items
      - in: query
        name: query
        description: Query string to search on
      - in: query
        name: sources
        description: List of sources to retrieve items from
      - in: query
        name: source_countries
        description: Search against only sources from the specified countries
      - in: query
        name: source_filter_mode
        description: Enables source_filter_name and indicates filtering type
      - in: query
        name: source_filter_name
        description: Limit items to a predefined list of sources
      responses:
        200:
          description: OK
      tags:
      - News
      - Sources
  topic/{guid}/sources/:
    get:
      summary: Topic Sources
      description: The guid for the topic.
      operationId: getTopicGuSources
      x-api-path-slug: topicguidsources-get
      parameters:
      - in: query
        name: access_key
        description: Unique API access key
      - in: query
        name: from_date
        description: Beginning of date range for which items are searched
      - in: query
        name: offset
        description: Number of items to skip before beginning the result set
      - in: query
        name: pagesize
        description: Number of items to return
      - in: query
        name: sources
        description: List of sources to retrieve items from
      - in: query
        name: source_countries
        description: Search against only sources from the specified countries
      - in: query
        name: source_filter_mode
        description: Enables source_filter_name and indicates filtering type
      - in: query
        name: source_filter_name
        description: Limit items to a predefined list of sources
      - in: path
        name: Topic Sources
        description: The guid for the topic
      - in: query
        name: to_date
        description: End of date range for which items are searched
      responses:
        200:
          description: OK
      tags:
      - News
      - Topic
      - Sources
  source/:
    get:
      summary: Source
      description: Returns the source represented by the specified GUID.
      operationId: getSource
      x-api-path-slug: source-get
      parameters:
      - in: query
        name: access_key
        description: Unique API access key
      - in: path
        name: GUID
        description: GUID representing news source
      responses:
        200:
          description: OK
      tags:
      - Source
  source/{GUID}/articles/:
    get:
      summary: Source Articles
      description: Returns a list of articles provided by the specified source
      operationId: getSourceGuArticles
      x-api-path-slug: sourceguidarticles-get
      parameters:
      - in: query
        name: access_key
        description: Unique API access key
      - in: query
        name: article_filter_mode
        description: Enables article_filter_name and indicates filtering type
      - in: query
        name: article_filter_name
        description: Limit items to a predefined list of articles
      - in: query
        name: categories
        description: Limit items to the categories specified
      - in: query
        name: from_date
        description: Beginning of date range for which items are searched
      - in: query
        name: get_topics
        description: Set to true to include associated topics inline with each article
      - in: query
        name: has_images
        description: Return only articles that have associated images (accessible
          via article/GUID/images)
      - in: query
        name: languages
        description: Limit items to those in the specified language
      - in: query
        name: licensed
        description: Search exclusively for fully licensed, full text content
      - in: query
        name: media_types
        description: Limit the media type of the returned items
      - in: query
        name: offset
        description: Number of items to skip before beginning the result set
      - in: query
        name: pagesize
        description: Number of items to return
      - in: query
        name: sort
        description: Sort order for returned items
      - in: query
        name: topics
        description: List of topics to retrieve items from
      - in: query
        name: topic_filter_mode
        description: Enables topic_filter_name and indicates filtering type
      - in: query
        name: topic_filter_name
        description: Limit items to a predefined list of topics
      - in: query
        name: to_date
        description: End of date range for which items are searched
      responses:
        200:
          description: OK
      tags:
      - News
      - Source
      - GUID
      - Articles
  source/{GUID}/topics/:
    get:
      summary: Source Topics
      description: Returns a list of topics related to the source specified by the
        given GUID.
      operationId: getSourceGuTopics
      x-api-path-slug: sourceguidtopics-get
      parameters:
      - in: query
        name: access_key
        description: Unique API access key
      - in: query
        name: from_date
        description: Beginning of date range for which items are searched
      - in: query
        name: offset
        description: Number of items to skip before beginning the result set
      - in: query
        name: pagesize
        description: Number of items to return
      - in: query
        name: topics
        description: List of topics to retrieve items from
      - in: query
        name: topic_classifications
        description: Limit results to those with the specified topic classification
      - in: query
        name: topic_filter_mode
        description: Enables topic_filter_name and indicates filtering type
      - in: query
        name: topic_filter_name
        description: Limit items to a predefined list of topics
      - in: query
        name: topic_subclassifications
        description: Limit results to those with the specified topic sub-classification
      - in: query
        name: to_date
        description: End of date range for which items are searched
      responses:
        200:
          description: OK
      tags:
      - News
      - Source
      - GUID
      - Topics
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---