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
  <div class="container">
    <div class="background-image"></div>
    <div class="form-container">
      <div class="form-inner">
        {#if submissionStatus}
          <div class="message">{submissionStatus}</div>
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
      </div>
    </div>
  </div>
</main>

<style>
  main {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 90%;
    overflow: hidden;
  }

  .container {
    position: relative;
    max-width: 90%;
    width: 90%;
    height: 80vh;
    margin: 0 auto;
    display: flex;
    background: url("images/main/scribble2.jpg") no-repeat center;
    background-size: contain;
    background-position: center;
  }

  .form-container {
    position: relative;
    z-index: 1;
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    border-radius: 10px;
    padding: 3%;
  }

  .message {
    font-weight: bold;
    color: black;
    text-align: center;
    padding: 10px;
    background-color: #f2f2f2;
    border: 1px solid #ccc;
    border-radius: 2px;
    font-size: 14px;
    margin-top: 10px; /* Add 10px top margin to create the gap */
  }

  .form-inner {
    max-width: 45%;
    width: 100%; /* Center the form horizontally */
    padding-top: 38%;
  }

  label {
    font-weight: bold;
    color: #333;
    font-size: 12px;
  }

  input,
  textarea {
    width: 100%;
    padding: 3%;
    margin-bottom: 3%;
    border: 1px solid #ccc;
    border-radius: 5px;
    font-size: 12px;
  }

  textarea {
    resize: none;
    height: 90px;
    padding-top: 20px; /* Adjusted top padding */
  }

  button {
    align-items: center;
    width: 50%;
    padding: 3%;
    background-color: #000000;
    color: #fff;
    border: none;
    cursor: pointer;
    font-size: 12px;
  }

  @media screen and (max-width: 768px) {
    .form-inner {
      width: 50%;
      max-width: 70%;
  
    }
    textarea {
      height: 80px;
    }
  }

  @media screen and (max-width: 550px) {
    .form-inner {
      width: 50%; /* Decrease the form width at this breakpoint */
      max-width: 80%;
      min-height: 300px; /* Add a minimum height to the form */
    }
    textarea {
      height: 70px; /* Decrease the textarea height at this breakpoint */
    }

    .form-container {
      max-height: 40%;
      padding-top: 15%;
    }
  }

  @media screen and (max-width: 510px) {
    .form-container{
padding-top: 15%;
}
  }

  
  @media screen and (max-width: 425px) {
    .form-inner {
      width: 60%;
      max-width: 90%;
    }
    textarea {
      height: 50px;
    }
  }


  @media screen and (max-width: 380px) {
    .form-inner {
      width: 50%;
      max-width: 90%;
    }
    textarea {
      height: 45px;
    }
  }

  @media screen and (max-width: 325px) {
    .form-inner {
      width: 45%;
      max-width: 70%;
    }
    textarea {
      height: 40px;
    }
    .message{
      font-size: 5px;
    }
  }
</style>
