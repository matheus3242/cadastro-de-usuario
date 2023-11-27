        
        fetch('https://servicodados.ibge.gov.br/api/v1/localidades/estados')
            .then(response => response.json())
            .then(data => {
                const ufSelect = document.getElementById('uf');
                data.forEach(estado => {
                    const option = document.createElement('option');
                    option.value = estado.sigla;
                    option.textContent = estado.sigla;
                    ufSelect.appendChild(option);
                });
            });

       
        document.getElementById('uf').addEventListener('change', function () {
            const uf = this.value;
            document.getElementById('regiao').value = '';
            document.getElementById('cidade').innerHTML = '';

            fetch(`https://servicodados.ibge.gov.br/api/v1/localidades/estados/${uf}`)
                .then(response => response.json())
                .then(data => {
                    document.getElementById('regiao').value = data.regiao.nome;
                });

            fetch(`https://servicodados.ibge.gov.br/api/v1/localidades/estados/${uf}/municipios`)
                .then(response => response.json())
                .then(data => {
                    const cidadeSelect = document.getElementById('cidade');
                    data.forEach(cidade => {
                        const option = document.createElement('option');
                        option.value = cidade.nome;
                        option.textContent = cidade.nome;
                        cidadeSelect.appendChild(option);
                    });
                });
        });

        function salvarCadastro() {
            const cadastro = {
                nome: document.getElementById('nome').value,
                genero: document.getElementById('genero').value,
                idade: document.getElementById('idade').value,
                uf: document.getElementById('uf').value,
                regiao: document.getElementById('regiao').value,
                cidade: document.getElementById('cidade').value,
                telefone: document.getElementById('telefone').value,
                email: document.getElementById('email').value
            };

           
            const cadastros = [];
            cadastros.push(cadastro);

           
            document.getElementById('cadastroForm').reset();

            console.log('Cadastro salvo:', cadastro);
        }

        function excluirCadastros() {
            
            const cadastros = [];

            console.log('Cadastros excluídos');
        }
