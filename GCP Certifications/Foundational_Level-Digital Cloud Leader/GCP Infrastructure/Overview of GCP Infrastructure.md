# GCP Infrastructure

## Regions 🌍
- A region is a specific geographical location where you can host your resources.
- Each region is an independent geographic area that consists of multiple zones.
- Regions help you place your resources closer to your users to reduce latency and meet regulatory and compliance requirements.
- Regions are categorized into following geographies:
  - Americas
  - Europe
  - Middle East
  - Asis Pacific
  - Others
- At present, there 42 working regions.
- CLI to see the list of all regions: gcloud compute regions list
- You can also opt to host your resources in more than one region.
- Using multiple regions can enhance disaster recovery strategies by provoding geographic redundancy.
- Some regions are designed to be more environmentally friendly, with low CO2 emissions.
- Each region contains multiple zones. A zone is an isolated location within a region, designed to be independent of other zones in the same region.
- This setup provides redundancy and isolation, ensuring high availability, and fault tolerance for your applications.
- Each region in Google Cloud Platform contains a minimum of three zones. This setup ensures redundancy and high availability, allowing you to distribute your
  resources across multiple zones within a regino to protect against failures. 



## Zones 🗺️
- A zone is an isolated location within a region. Each region has multiple zones, and each zone is designed to be independent of the others in the same region.
- Zones provide redundancy and isolation. By distributing your resources across multiple zones, you can protect your applications from failures that might occur 
  in a single zone.
- In the us-central1 region, the zones are us-central1-a, us-central1-b, us-central1-c, and us-central1-f.

## Key Points to Highlight 📌
- High Availability: Deploying resources across multiple zones within a region ensures high availability and fault tolerance.
- Low Latency: Regions and zones help minimize latency by allowing you to place resources closer to your users.
- Disaster Recovery: Using multiple regions can enhance disaster recovery strategies by providing geographic redundancy.


