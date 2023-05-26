# NN API Docs

<code-method>

<code-copy>

Welcome to the NN API Docs! Your one stop shop to find out all about our APIs we have marked as being ready for prime-time. A curated list if you will of APIs that demonstrate the quality of our API landscape.

We have language bindings in cURL, TypeScript, Java and Python. You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

## Applying a product mindset

When approaching APIs, it is essential for engineers and architects to adopt a mindset that considers APIs as products rather than just technical components. Treating APIs as products emphasizes the need for careful planning, design, and maintenance throughout their lifecycle. Firstly, it is crucial to identify and understand the target audience and their specific needs. Just like any product, APIs should be user-centered, providing intuitive and well-documented interfaces. This involves creating clear and comprehensive documentation, sample code, and interactive tools that facilitate adoption and integration. Additionally, product thinking requires regular assessment and improvement of APIs based on user feedback and usage analytics. This iterative approach ensures that APIs evolve to meet the changing needs of their consumers. Lastly, providing support and engaging in active communication with API users are key aspects of maintaining a successful product. By adopting a product mindset, engineers and architects can enhance the usability, accessibility, and overall value of APIs, resulting in better developer experiences and successful integrations.

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
