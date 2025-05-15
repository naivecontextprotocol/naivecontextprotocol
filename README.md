# naivecontextprotocol
This is a single-page spec for solving the context problem for large language models.

## Why?
I realize this is a competing standard to Model Context Protocol,
But after spending many hours implementing simple MCP servers and following the development of the protocol,
I think MCP sucks, so I started making NCP everything, I believe, MCP should've been.

Feedback & contribution welcome.

Goals:
- Simple to implement
- Use existing standards and best practices
- Hostable on a basic HTTP server
- Community driven

![Standard](https://imgs.xkcd.com/comics/standards_2x.png)


## Spec
- Use OpenAPI for tool discovery (by default hosted on `/.well-known/ncp-tools.json` but can be configured on the client)
- Use JSON Schema for tool definition (With OpenAPI)
- Use HTTP for tool calling
- Use OpenAPI for defining Authorization

`ncp-tools.json` is an OpenAPI specification for the tools that are available on this server 
and how to call them.

### Resources
Within the `ncp-tools.json`, use OpenAPI tags:
- `resource_list` to annotate the endpoint for listing resources
- `resource_read` to annotate the endpoint for fetching the resource

### Prompts
Within the `ncp-tools.json` use OpenAPI tags:
- `prompt_list` to annotate the endpoint for listing prompts
- `prompt_read` to annotate the endpoint for fetching the prompt

## Contribution
Please create a pull request.

Tasks:
- [ ] Define the input & output for resource endpoints
- [ ] Define the input & output for the prompt endpoints
- [ ] Add examples to the spec
- [ ] Explain the advantages
- [ ] Add a section for real-time communication
- [ ] Make an example server (hosted)
- [ ] Make an MCP server that uses NCP behind the scene to make adoption easier
- [ ] Expand on the Authorization
- [ ] Create a reference implenetation (if needed)

