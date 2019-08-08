# Fetch API script
prepared for my portfolio site. 
It looks like this:
```
const list = document.querySelector('.list--js');
fetch('https://api.github.com/users/mrozrafal/repos?sort=updated&direction=desc')
.then(resp => resp.json())
.then(resp => {
  const repos = resp;
for (const repo of repos){
  const {description, html_url, name} = repo;
list.innerHTML+= `
<li class="list__item">
<a class="list__link" href ="${html_url}">${name}</a>
<p class="link__description">
${description ? description : "no description" } 
</p>
</li>
`;
}
})
.catch(err =>{
  console.log(err);
})
```
