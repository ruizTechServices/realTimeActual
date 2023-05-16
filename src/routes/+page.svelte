<script>
    import Card from "/src/components/card.svelte";
  
    let comment = "";
    let image = "";
    let comments = [];
  
    function handleFormSubmit(event) {
      event.preventDefault();
      console.log(comment);
      comments = [...comments, { id: comments.length + 1, content: comment, image: image }];
      comment = "";
      image = "";
    }
  </script>
  
  <div class="container grid grid-cols-2 grid-rows-6 gap-4 mx-auto MainCont">
    <div class="col-start-1 row-start-1 h-10 p-5 align-center">
      <h1>Type your Thoughts and Comments Below:</h1>
    </div>
    <form
      class="col-start-1 row-start-2 border-r-2 flex flex-col justify-between"
      on:submit={handleFormSubmit}
    >
      <label for="comment">Comment:</label>
      <input
        class="w-full h-10 px-3 text-base placeholder-gray-600 border rounded-lg focus:shadow-outline mb-4"
        id="comment"
        type="text"
        bind:value={comment}
        required
      />
      <label for="image">Image URL:</label>
      <input
        class="w-full h-10 px-3 text-base placeholder-gray-600 border rounded-lg focus:shadow-outline mb-4"
        id="image"
        type="text"
        bind:value={image}
        required
      />
      <button
        class="w-20 mx-auto mb-5 text-white bg-blue-500 rounded hover:bg-blue-700"
        type="submit">Submit</button
      >
    </form>
  
    <!--column 2 stuffs-->
    <div class="col-start-2 row-span-full">
      <div class="container" id="commentBox">
        <div class="flex flex-wrap justify-end">
          {#each comments as comment (comment.id)}
            <Card `{card}={comment}` />
          {/each}
        </div>
      </div>
    </div>
  </div>
  
  <style>
    .MainCont {
      height: 80vh;
    }
    #commentBox {
      height: 100%;
      overflow-y: scroll;
    }
  </style>
  