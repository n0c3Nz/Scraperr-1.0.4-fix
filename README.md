# Scraperr

Scraperr is a self-hosted web application that allows users to scrape data from web pages by specifying elements via XPath. Users can submit URLs and the corresponding elements to be scraped, and the results will be displayed in a table.

From the table, users can download a csv of the job's results, along with an option to rerun the job.

## Features

- Submit URLs for web scraping
- Add and manage elements to scrape using XPath
- Display results of scraped data
- Download csv containing results
- Rerun jobs

## Installation

1. Clone the repository:

   ```sh
   git clone https://github.com/jaypyles/scraperr.git
   cd scraperr
   ```

1. Deploy
   ```sh
   make up
   ```

The app provides its own `traefik` configuration to use independently, but can easily be reverse-proxied by any other app, or your own reverse-proxy.

## Usage

1. Open the application in your browser at `http://localhost`.
2. Enter the URL you want to scrape in the URL field.
3. Add elements to scrape by specifying a name and the corresponding XPath.
4. Click the "Submit" button to start the scraping process.
5. The results will be displayed in the "Results" section.

## API Endpoints

Use this service as an API for your own jobs.

- `/api/submit-scrape-job`: Endpoint to submit the scraping job. Accepts a POST request with the following payload:
  ```json
  {
    "url": "http://example.com",
    "elements": [
      {
        "name": "ElementName",
        "xpath": "/div[@class='example']"
      }
    ],
    "user": "user@example.com",
    "time_created": "2024-07-07T12:34:56.789Z"
  }
  ```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

### Contributions

Development made easy by developing from [webapp template](https://github.com/jaypyles/webapp-template]. View documentation for extra information.

Start development server:

`make deps build up-dev`
