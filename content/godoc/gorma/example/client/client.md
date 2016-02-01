
# client
    import "github.com/goadesign/gorma/example/client"







## type ActionCommand
``` go
type ActionCommand interface {
    // Run makes the HTTP request and returns the response.
    Run(c *Client) (*http.Response, error)
    // RegisterFlags defines the command flags.
    RegisterFlags(*kingpin.CmdClause)
}
```
ActionCommand represents a single action command as defined on the command line.
Each command is associated with a generated client method and contains the logic to
call the method passing in arguments computed from the command line.











## type Client
``` go
type Client struct {
    *goa.Client
}
```
Client is the cellar service client.









### func New
``` go
func New() *Client
```
New instantiates the client.




### func (\*Client) CreateAccount
``` go
func (c *Client) CreateAccount(path string, payload *CreateAccountPayload) (*http.Response, error)
```
Create new account



### func (\*Client) CreateBottle
``` go
func (c *Client) CreateBottle(path string, payload *CreateBottlePayload) (*http.Response, error)
```
Record new bottle



### func (\*Client) DeleteAccount
``` go
func (c *Client) DeleteAccount(path string) (*http.Response, error)
```
DeleteAccount makes a request to the delete action endpoint of the account resource



### func (\*Client) DeleteBottle
``` go
func (c *Client) DeleteBottle(path string) (*http.Response, error)
```
DeleteBottle makes a request to the delete action endpoint of the bottle resource



### func (\*Client) ListBottle
``` go
func (c *Client) ListBottle(path string, years []int) (*http.Response, error)
```
List all bottles in account optionally filtering by year



### func (\*Client) RateBottle
``` go
func (c *Client) RateBottle(path string, payload *RateBottlePayload) (*http.Response, error)
```
RateBottle makes a request to the rate action endpoint of the bottle resource



### func (\*Client) ShowAccount
``` go
func (c *Client) ShowAccount(path string) (*http.Response, error)
```
Retrieve account with given id



### func (\*Client) ShowBottle
``` go
func (c *Client) ShowBottle(path string) (*http.Response, error)
```
Retrieve bottle with given id



### func (\*Client) UpdateAccount
``` go
func (c *Client) UpdateAccount(path string, payload *UpdateAccountPayload) (*http.Response, error)
```
Change account name



### func (\*Client) UpdateBottle
``` go
func (c *Client) UpdateBottle(path string, payload *UpdateBottlePayload) (*http.Response, error)
```
UpdateBottle makes a request to the update action endpoint of the bottle resource



## type CreateAccountPayload
``` go
type CreateAccountPayload struct {
    // Name of account
    Name string
}
```
CreateAccountPayload is the data structure used to initialize the account create request body.











## type CreateBottlePayload
``` go
type CreateBottlePayload struct {
    Color     string
    Country   *string
    Name      string
    Region    *string
    Review    *string
    Sweetness *int
    Varietal  string
    Vineyard  string
    Vintage   int
}
```
CreateBottlePayload is the data structure used to initialize the bottle create request body.











## type RateBottlePayload
``` go
type RateBottlePayload struct {
    // Rating of bottle between 1 and 5
    Rating int
}
```
RateBottlePayload is the data structure used to initialize the bottle rate request body.











## type UpdateAccountPayload
``` go
type UpdateAccountPayload struct {
    // Name of account
    Name string
}
```
UpdateAccountPayload is the data structure used to initialize the account update request body.











## type UpdateBottlePayload
``` go
type UpdateBottlePayload struct {
    Color     *string
    Country   *string
    Name      *string
    Region    *string
    Review    *string
    Sweetness *int
    Varietal  *string
    Vineyard  *string
    Vintage   *int
}
```
UpdateBottlePayload is the data structure used to initialize the bottle update request body.

















- - -
Generated by [godoc2md](http://godoc.org/github.com/davecheney/godoc2md)