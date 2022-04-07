# blooket-tokens
if (tokens > 500) {
    alert('You can only add up to 500 tokens daily.')
}

const response = await fetch('https://api.blooket.com/api/users/add-rewards', {
    method: "PUT",
    headers: {
        "referer": "https://www.blooket.com/",
        "content-type": "application/json",
        "authorization": localStorage.token
    },
    body: JSON.stringify({
        addedTokens: tokens,
        addedXp: 300,
        name: await getName(myToken)
    })
});

if (response.status == 200) {
    alert(`${tokens} tokens and 300 XP added to your account!`);
} else {
    alert('An error occured.');
};
