# NN API Docs

<code-method>

<code-copy>

Welcome to the NN API Docs! Your one stop shop to find out all about our APIs we have marked as being ready for prime-time. The APIs in this list are all run as a product which means you can safely assume the quality is up to par and you as the user are treated as the customer.

We have language bindings in cURL, TypeScript, Java and Python so you can use and test the code examples in your environment quickly.

## Our APIs and our product mindset

When approaching APIs, it is essential for engineers and architects to adopt a mindset that considers APIs as products rather than just technical components. Treating APIs as products emphasizes the need for careful planning, design, and maintenance throughout their lifecycle. Firstly, it is crucial to identify and understand the target audience and their specific needs. Just like any product, APIs should be user-centered, providing intuitive and well-documented interfaces. This involves creating clear and comprehensive documentation, sample code, and interactive tools that facilitate adoption and integration. Additionally, product thinking requires regular assessment and improvement of APIs based on user feedback and usage analytics. This iterative approach ensures that APIs evolve to meet the changing needs of their consumers. Lastly, providing support and engaging in active communication with API users are key aspects of maintaining a successful product. By adopting a product mindset, engineers and architects can enhance the usability, accessibility, and overall value of APIs, resulting in better developer experiences and successful integrations.

## API Layers

The NN APIs are divided into three layers, each serving a distinct purpose: Experience, Product, and Platform.

### Experience Layer

The Experience Layer focuses on providing a seamless and intuitive interaction between developers and the API. It aims to enhance the developer experience by offering easy-to-use tools, comprehensive documentation, and robust support. This layer prioritizes usability, ensuring that developers can quickly understand and integrate the API into their applications. The Experience Layer plays a crucial role in reducing the learning curve, providing clear examples, code snippets, and interactive resources that guide developers in effectively utilizing the API's capabilities. By focusing on the Experience Layer, engineers and architects can foster a positive user experience and encourage widespread adoption of the API.

### Product Layer

The Product Layer considers the API as a standalone product with its own set of features, functionalities, and value propositions. It involves strategic planning, market research, and understanding the needs of the target audience. Engineers and architects in this layer envision the API as a solution to specific problems, addressing the pain points of developers and providing value-added services. Just like any product, the API at the Product Layer requires continuous improvement and iteration based on user feedback and market demands. This layer also involves defining pricing models, licensing terms, and business strategies that align with the overall product vision. By treating the API as a product, engineers and architects can create a compelling offering that meets market demands and drives business growth.

### Platform Layer

The Platform Layer focuses on the infrastructure and technical aspects of the API. It deals with the underlying systems, scalability, performance, security, and interoperability. Engineers and architects at this layer ensure that the API is built on a solid foundation, adhering to industry standards and best practices. They design a scalable and robust architecture that can handle high volumes of requests and provide reliable services. The Platform Layer also involves implementing security measures, such as authentication, authorization, and encryption, to safeguard the API and its users. Additionally, it emphasizes interoperability, allowing the API to seamlessly integrate with other systems and technologies. By focusing on the Platform Layer, engineers and architects create a stable and efficient infrastructure that supports the reliable and secure operation of the API.

By recognizing and addressing the distinct purposes of each layer, engineers and architects can develop and maintain APIs that offer exceptional experiences, are designed as valuable products, and are built on a solid platform foundation.

</code-copy>

</code-method>

# Authentication

<code-method>

<code-copy>

The NN API uses API keys to allow access to the API. You can register a new The NN API API key at our [developer portal](https://example.com/developers).

The NN API expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class=notice>
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

The NN API's API key authentication is a simplified approach to secure API access. It provides a basic level of authentication by requiring the API key to be included in the request header. This helps verify the identity of the requester and grants access to the API resources. However, it's important to note that this method may not be suitable for all security requirements.

For advanced security measures, The NN API provides additional documentation on topics such as ForgeRock, JWT exchange, and device binding. ForgeRock is a comprehensive identity and access management platform that can be integrated with The NN API's API for enhanced security controls. It offers features like single sign-on, user provisioning, and fine-grained access management.

JWT (JSON Web Tokens) exchange is another advanced topic worth exploring. By implementing JWT-based authentication, The NN API can generate and exchange tokens securely, allowing users to access protected resources. JWTs can carry information about the user and their permissions, providing a stateless and scalable solution for authentication and authorization.

Device binding is yet another important aspect of securing API access. It involves binding the API key to a specific device, ensuring that requests can only be made from that authorized device. This prevents unauthorized usage of the API key even if it gets compromised.

For more detailed information and implementation guidelines on these advanced topics, please refer to the respective documentation provided by The NN API. These measures enable you to tailor the security of your API integration based on your specific needs and ensure the protection of sensitive data.

</code-copy>

<code-example>

> To authorize, use this code:

```ruby
require 'The NN API'

api = The NN API::APIClient.authorize!('meowmeowmeow')
```

```python
import The NN API

api = The NN API.authorize('meowmeowmeow')
```

```bash
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
import { The NN API } from "The NN API";

const api = The NN API.authorize("meowmeowmeow");
```

> Make sure to replace `meowmeowmeow` with your API key.

</code-example>

</code-method>

# Customers

## Get All Customers

<code-method>

<code-copy>

This endpoint retrieves all customers.

### HTTP Request

`GET https://example.com/api/kittens`

### Query Parameters

| Parameter    | Default | Description                                                                      |
| ------------ | ------- | -------------------------------------------------------------------------------- |
| include_cats | false   | If set to true, the result will also include cats.                               |
| available    | true    | If set to false, the result will include kittens that have already been adopted. |

<aside class=success>
Remember — a happy kitten is an authenticated kitten!
</aside>

</code-copy>

<code-example>

```ruby
require 'The NN API'

api = The NN API::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import The NN API

api = The NN API.authorize('meowmeowmeow')
api.kittens.get()
```

```bash
curl "https://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
import { The NN API } from "The NN API";

const api = The NN API.authorize("meowmeowmeow");
const kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

</code-example>

</code-method>

## Get a Specific Kitten

```ruby
require 'The NN API'

api = The NN API::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import The NN API

api = The NN API.authorize('meowmeowmeow')
api.kittens.get(2)
```

```bash
curl "https://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
import { The NN API } from "The NN API";

const api = The NN API.authorize("meowmeowmeow");
const max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class=warning>
Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.
</aside>

### HTTP Request (with ID)

`GET https://example.com/kittens/<ID>`

### URL Parameters

| Parameter | Description                      |
| --------- | -------------------------------- |
| ID        | The ID of the kitten to retrieve |
