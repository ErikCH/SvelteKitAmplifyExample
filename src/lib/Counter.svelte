<script>
  import Amplify from "aws-amplify";
  import { Auth } from "aws-amplify";
  // Add exports
  Amplify.configure({});

  let count = 0;

  async function signIn() {
    try {
      const username = "test";
      const password = "test123";
      const user = await Auth.signIn(username, password);
    } catch (error) {
      console.log("error signing in", error);
    }
  }

  const increment = async () => {
    //     await signIn();

    count += 1;
  };
</script>

<button on:click={signIn}> Sign In Test </button>

<button on:click={increment}>
  Clicks: {count}
</button>

<style>
  button {
    font-family: inherit;
    font-size: inherit;
    padding: 1em 2em;
    color: #ff3e00;
    background-color: rgba(255, 62, 0, 0.1);
    border-radius: 2em;
    border: 2px solid rgba(255, 62, 0, 0);
    outline: none;
    width: 200px;
    font-variant-numeric: tabular-nums;
  }

  button:focus {
    border: 2px solid #ff3e00;
  }

  button:active {
    background-color: rgba(255, 62, 0, 0.2);
  }
</style>
