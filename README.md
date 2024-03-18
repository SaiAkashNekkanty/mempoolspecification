# Mining Pools Mempool API

This API provides statistics about mining pools' activities in the last 24 hours.

## Endpoints

### GET /mining/pools/24h

Retrieves mining pool statistics for the last 24 hours.

#### Responses

- **200 OK**: Successful response containing mining pool statistics.
  - Content Type: `application/json`
  - Schema: [MiningPool](#miningpool)

## Data Structures

### MiningPool

A JSON object representing mining pool statistics for the last 24 hours.

| Field                | Type     | Description                                       |
|----------------------|----------|---------------------------------------------------|
| pools                | Array    | An array of [Pool](#pool) objects representing individual mining pools. |
| blockCount           | Integer  | Total number of blocks mined in the last 24 hours. |
| lastEstimatedHashrate| Number   | Last estimated hashrate.                         |

### Pool

A JSON object representing an individual mining pool.

| Field          | Type     | Description                                                |
|----------------|----------|------------------------------------------------------------|
| poolId         | Integer  | The unique ID of the pool.                                 |
| name           | String   | The name of the mining pool.                               |
| link           | String   | The URL of the mining pool's website (in URI format).       |
| blockCount     | Integer  | Number of blocks mined by the pool in the last 24 hours.   |
| rank           | Integer  | The ranking of the pool based on blocks mined in the last 24 hours. |
| emptyBlocks    | Integer  | Number of empty blocks mined by the pool in the last 24 hours. |
| slug           | String   | A unique identifier for the pool.                          |
| avgMatchRate   | Number   | Average match rate of the pool's blocks in the last 24 hours. |
| avgFeeDelta    | String   | Average fee delta of the pool's blocks in the last 24 hours. |
| poolUniqueId   | Integer  | The unique ID of the pool.                                 |

## Usage

Make a GET request to `/mining/pools/24h` to retrieve mining pool statistics for the last 24 hours in JSON format.

```bash
curl -X GET "https://api.example.com/mining/pools/24h" -H "accept: application/json"
