
// Usage
class ClassComponent extends React.Component {
  render() {
    const { data: session, status } = this.props.session
    return null
  }
}

const ClassComponentWithSession = withSession(ClassComponent)
```

# Render Prop

```Node.js
import { userSession } from "next-auth/react"

const UserSession = ({ children }) => {
  const session = userSession()
  return children(session)
}

// Usage
class ClassComponent extends React.Component {
  render() {
    return (
      <UserSession>
        {(session) => <pre>{JSON.stringify(session, null, 2)}</pre>}
      </UserSession>
    )
  }
}

