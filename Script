let form = document.getElementById('form')
let username = document.getElementById('username')
let email = document.getElementById('email')
let password = document.getElementById('password')
let passwordConfirmation = document.getElementById('password-confirmation')

form.addEventListener('submit', (e) => {
   e.preventDefault();
    
   checkInputs();
  });

function checkInputs(){
  let usernameValue = username.value;
  let emailValue = email.value;
  let passwordValue = password.value;
  let passwordConfirmationValue = passwordConfirmation.value;
  
  //usuário
  if(usernameValue === ''){
    setErrorFor(username, 'O nome de usuário é obrigatório!');
  } else{
    setsuccessfor(username);
  }

  //email
  if(emailValue === ''){
    setErrorFor(email, 'O email é obrigatório!')
  } else if(!checkEmail(emailValue)){
    setErrorFor(email,'Este email é inválido!')

  } else{
    setsuccessfor(email)

  }

  //senha
  if(passwordValue === ''){
  setErrorFor(password, 'Crie uma senha para o seu usuário!')
  } else if(passwordValue.length < 7){
    setErrorFor(password, 'A senha deve ter no mínimo 7 caracteres!')
  } else if(passwordValue != passwordConfirmationValue){
    setErrorFor(password, 'As senhas devem ser iguais!')
  }else{
    setsuccessfor(password)
  }
  
  
  //confirmação de senha
  if(passwordConfirmationValue === ''){
    setErrorFor(passwordConfirmation, 'Confirme a sua senha!')

  } else if(passwordConfirmationValue != passwordValue){
    setErrorFor(passwordConfirmation, 'As senhas devem ser iguais!')

  } else{
    setsuccessfor(passwordConfirmation)
  }

  //confirmar dados corretos
  
  let confirme =  document.getElementById('Confirme')
  
  let formControls = form.querySelectorAll('.form-control');

  let formIsValid = [...formControls].every((formControl)=>{
    return(formControl.className ===  'form-control success');
  });

  if(formIsValid) {
    confirme.innerHTML = `Parabéns ${usernameValue}.`
    confirme.innerHTML += '<p> A sua conta foi criada com sucesso. </p>'
    //console.log('O formulário está válido!')
  }
}

function setErrorFor(input, message) {
  let formControl = input.parentElement;
  let small = formControl.querySelector("small");

  // Adicionar mensagem de erro
  small.innerText = message;
  
  // Adicionar Classe de erro
  formControl.className = 'form-control error';
}

function setsuccessfor (input){
  let formControl = input.parentElement;

  // adicionar a classe sucesso
  formControl.className = 'form-control success';
}

 //validação de e-mail
function checkEmail(email) {
  return /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/.test(
    email
  );
}
