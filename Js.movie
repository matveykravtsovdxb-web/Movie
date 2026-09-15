document.getElementById('searchBtn').addEventListener('click', function() {
    // 1. Get the title the user typed in
    const title = document.getElementById('movieInput').value;
    const apiKey = 'YOUR_API_KEY'; // <-- Paste your OMDb key here
    const url = `https://omdbapi.com{encodeURIComponent(title)}&apikey=${apiKey}`;
    const container = document.getElementById('movieContainer');

    // 2. Fetch the data from the website
    fetch(url)
        .then(response => response.json())
        .then(data => {
            if (data.Response === "True") {
                // 3. Display the movie info on the screen if found
                container.innerHTML = `
                    <h2>${data.Title} (${data.Year})</h2>
                    <p><strong>Plot:</strong> ${data.Plot}</p>
                    <img src="${data.Poster}" alt="Poster" style="max-width:200px;">
                `;
            } else {
                container.innerHTML = `<p style="color:red;">Movie not found!</p>`;
            }
        })
        .catch(error => {
            console.error('Something went wrong:', error);
        });
});
