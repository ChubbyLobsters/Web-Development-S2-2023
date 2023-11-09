<script>
  let name = "";
  let email = "";
  let message = "";
  let submissionStatus = null;

  const handleSubmit = async () => {
    if (submissionStatus === "Form Has Been Received") {
      if (confirm("Another submission has been made. Are you sure you want to submit a new message?")) {
        resetForm();
      }
    } else {
      // Handle the form submission here
      submissionStatus = "Form Has Been Received";
    }
  }

  const resetForm = () => {
    name = "";
    email = "";
    message = "";
    submissionStatus = null;
  }
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
  
    <button type="submit">Submit</button>
  </form>
</main>

<style>   /* forms style sorced from stackOverflow */
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 700px; 
    background-image: url("images/main/scribble2.jpg");
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
    resize: none;
    height: 150px; 
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

  p {
    color: black;
    font-weight: bold;
    text-align: center;
    margin-top: 10px;
  }
</style>
