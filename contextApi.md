## context API

Today, a lot of people are using conext API instead Redux,
in order to use the Context API provided by React. Context provides a way to share data
between components without passing a prop to all the child components. 
Sounds pretty similar to Redux, doesn't it? in the practical example it is evident that it is even more similar than we think.

Let's see a basic example where we can use the Context API. We will fetched some GitHub issues of the booking ui
project and will rendered on the screen using context API

<a href="https://github.com/carlosHGit/context-api-issues">context Api project</a>.


# 1) Creating our first context

`context-api-issues/src/contexts/Issue.jsx`
The first thing we need to do is to create the issue context. For this, we create a folder
called contexts inside the src folder and then inside that, we add the Issue.jsx file.

The first thing we do after this, is to create our context by using the createContext
function and define the value we want to export:

`
export const IssueContext = createContext({
  issues: [],
  url: ''
})
`

then we create the issue provider, which will be in charge of receiving the properties and the children that will be within the scope of the context state

`
const IssueProvider = ({ children, url }) => {

  const [issues, setIssues] = useState([])

  const fetchIssues = useCallback(async () => {
    const response = await axios(url)

    if (response) {
      setIssues(response.data)
    }
  }, [url])


  useEffect(() => {
    fetchIssues()
  }, [fetchIssues])

  const context = {
    issues,
    url
  }

  return <IssueContext.Provider value={context}>{children}</IssueContext.Provider>
}`

# 2) Wrapping our components with the provider

The way we consume a context is divided into two parts. The first one is where we wrap
the app with the context provider.

`context-api-issues/src/components/App.jsx`

# 3) Consuming context with useContext
Now you can consume the context in the Issues component by using the useContext Hook.
Notice that here we are importing the IssueContext context.

`context-api-issues/src/components/Issues.jsx`

