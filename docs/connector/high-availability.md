# High availability

The connector is a very important component, therefore we recommend a high available deployment.

If one of the connector fails either because of a network issue or hardware issue, Auth0 can redirect the login transactions to the other connector.

Having a High Available deployment also allows updating the connector with zero downtime.

## Instructions

1. Install the connector as explained [here](@@env.BASE_URL@@/connector/install).
2. Once the first connection is up and running, move to the next point.
3. Copy the **config.json**, **lib/profileMapper.js** and **certs** from:
  -  Windows: `C:\Program Files (x86)\Auth0\AD LDAP Connector\`
  -  Linux: `/opt/auth0/ad-ldap`

4. Install the connector on a second server using the same instructions as above for the first server, when prompted for the Ticket URL close the dialog.
5. Overwrite the the **config.json**, **lib/profileMapper.js** and **certs** on the second server using the files from the first server.
6. Restart the service on the second server.

You should see now 2 connectors on the dashboard.