# insurance-orders

A Node.js app that serves as an API into the orders database for the [insurance-store-front][store_front_url]. To store the insurance policy orders, we use a [Cloudant NoSQL DB][cloudant_url].

In order to deploy the full set of microservices involved in the insurance-store demo, check out the [insurance-toolchain repo][toolchain_url].

[![Deploy to Bluemix](https://bluemix.net/deploy/button.png)](https://bluemix.net/deploy)

## Running the app on Bluemix

1. If you do not already have a Bluemix account, [sign up here][bluemix_reg_url]

2. Download and install the [Cloud Foundry CLI][cloud_foundry_url] tool

3. Clone the app to your local environment from your terminal using the following command:

  ```
  git clone https://github.com/IBM-Bluemix/insurance-orders.git
  ```

4. `cd` into this newly created directory

5. Open the `manifest.yml` file and change the `host` value to something unique.

  The host you choose will determinate the subdomain of your application's URL:  `<host>.mybluemix.net`

6. Connect to Bluemix in the command line tool and follow the prompts to log in

  ```
  $ cf login -a https://api.ng.bluemix.net
  ```

7. Create the [Cloudant service][cloudant_service_url] in Bluemix

  ```
  $ cf create-service cloudantNoSQLDB Shared policy-db
  ```

8. Push the app to Bluemix.

  ```
  $ cf push
  ```

And voila! You now have your very own instance of the Insurance Orders API running on Bluemix.

## Troubleshooting

The primary source of debugging information for your Bluemix app is the logs. To see them, run the following command using the Cloud Foundry CLI:

  ```
  $ cf logs insurance-orders --recent
  ```
For more detailed information on troubleshooting your application, see the [Troubleshooting section](https://www.ng.bluemix.net/docs/troubleshoot/tr.html) in the Bluemix documentation.

<!--Links-->
[store_front_url]: https://github.com/IBM-Bluemix/insurance-store-front
[toolchain_url]: https://github.com/IBM-Bluemix/insurance-toolchain
[bluemix_reg_url]: http://ibm.biz/insurance-store-registration
[cloud_foundry_url]: https://github.com/cloudfoundry/cli
[cloudant_url]: https://cloudant.com/
[cloudant_service_url]: https://new-console.ng.bluemix.net/catalog/services/cloudant-nosql-db/