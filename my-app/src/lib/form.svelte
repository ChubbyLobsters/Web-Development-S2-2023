<script>
  import { onMount } from "svelte";

  let name = "";
  let email = "";
  let message = "";
  let submissionStatus = null;
</script>

<main>
  {#if submissionStatus}
    <p>{submissionStatus}</p>
  {/if}
  <form on:submit={handleSubmit}>
    <label for="name">Name:</label>
    <input type="text" id="name" bind:value={name} required />
    
    <label for="email">Email:</label>
    <input type="email" id="email" bind:value={email} required />
  
    <label for="message">Message:</label>
    <textarea id="message" bind:value={message} required></textarea>
  
    {#if submissionStatus === "Sending..."}
      <button type="submit" disabled>Sending...</button>
    {:else}
      <button type="submit">Submit</button>
    {/if}
    
    {#if submissionStatus === "Error sending your message."}
      <p class="error-message">Error sending your message.</p>
    {/if}
  </form>
</main>


<style>
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 700px; /* Set a specific height to fit the image */
    background-image: url("images/main/scribble2.jpg"); /* Replace with your image URL */
    background-size: cover;
    background-position: center;
  }

  form {
    max-width: 550px;
    width: 80%;
    padding: 20px;
  }

  label {
    font-weight: bold;
    color: #333;
  }

  input,
  textarea {
    width: 100%;
    padding: 10px;
    margin-bottom: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }

  textarea {
    resize: none; /* Prevents stretching */
    height: 150px; /* Set a fixed height for the textarea */
  }

  button {
    align-items: center;
    width: 70%;
    padding: 10px;
    background-color: #000000;
    color: #fff;
    border: none;
    cursor: pointer;
  }

  .error-message {
    color: red;
  }
</style>
