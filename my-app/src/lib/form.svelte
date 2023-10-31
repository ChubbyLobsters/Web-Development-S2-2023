<script>
    import { onMount } from "svelte";
  
    let formData = {
      name: "",
      email: "",
      message: "",
    };
  
    let submissionStatus = null;
  
    const handleSubmit = async () => {
      // You would typically send this data to your server for email processing.
      // This is a placeholder function and does not send actual emails.
      try {
        const response = await fetch("/your-email-endpoint", {
          method: "POST",
          headers: {
            "Content-Type": "application/json",
          },
          body: JSON.stringify(formData),
        });
  
        if (response.ok) {
          submissionStatus = "Success! Your message has been sent.";
        } else {
          submissionStatus = "Error sending your message.";
        }
      } catch (error) {
        submissionStatus = "Error sending your message.";
      }
    };
  
    // Reset the form after submission
    onMount(() => {
      if (submissionStatus === "Success! Your message has been sent.") {
        formData = {
          name: "",
          email: "",
          message: "",
        };
      }
    });
  </script>
  
  <div class="bg-img">
  <main>
    {#if submissionStatus}
      <p>{submissionStatus}</p>
    {/if}
    <form on:submit={handleSubmit}>
      <label for="name">Name:</label>
      <input type="text" id="name" bind:value={formData.name} required />

      <label for="email">Email:</label>
      <input type="email" id="email" bind:value={formData.email} required />
  
      <label for="message">Message:</label>
      <textarea id="message" bind:value={formData.message} required></textarea>
  
      <button type="submit">Submit</button>
    </form>
  </main>
</div>




  <style>
 

    main {
      text-align: center;

    }
  
    form {
      max-width: 200px;
      margin: auto;
      text-align: middle;
      padding-left: 400px;
      margin-top:300px;

    }

    .bg-img {
  background-image: url("form.jpg");
  height: 800px;
  width: 80%;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;
}
  </style>
  