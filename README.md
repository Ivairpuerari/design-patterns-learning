# design-patterns-learning
Repositório de estudo sobre padrões de projeto - TL;DR


### Padrões Criacionais


- Abstract Factory:  
O padrão Abstract Factory é bastante comum no código Java. Muitas frameworks e bibliotecas o utilizam para fornecer uma maneira de estender e personalizar seus componentes padrão.

	Exemplos das principais bibliotecas Java:

		javax.xml.parsers.DocumentBuilderFactory#newInstance()
		javax.xml.transform.TransformerFactory#newInstance()
		javax.xml.xpath.XPathFactory#newInstance()

	O padrão é identificado por seus métodos que retornam um objeto fábrica. Em seguida, a fábrica é usada para criar subcomponentes específicos.

		Abstract Interface Object (IObject)
				IMethod();

		Concrete class of Object implements IObject (CObject)
				 Method();

		Abstract Interface Factory (IFactory)
					IObject IMethodBuild(Type)

		Concrete Factory implements IFactory (CFactory)
				IObject MethodBuild(Type)

		Business():
			IObject obj;
			
			Business(IFactory factory):
				this.obj = factory.IMethodBuild();
			
			Method():
				obj.Method();

		Main():
			Business business;
			IFactory fct;
			
			fct = new CFactory();
			
			business = Business(fct);
			
			business.Method();
			
- Factory method:  
	Define um método, que deve ser usado para criar objetos em vez da chamada direta ao construtor (operador new). As subclasses podem substituir esse método para alterar a classe de objetos que serão criados.	

	Identificação: Os métodos fábrica podem ser reconhecidos por métodos de criação, que criam objetos de classes concretas, mas os retornam como objetos de tipo ou interface abstrata.
	
		
		
		Abstract Interface Object (IObject)
				IMethod();

		Concrete class of Object implements IObject (CObject)
				 Method();

		Abstract Class Factory (AFactory)
					void show():
						print('Hello !');
					
					@override
					IObject MethodBuild(Type)

		Concrete Factory extends AFactory (CFactory)
				@override
				IObject MethodBuild(Type):
					retun new CObject();	

		Main():
			CFactory fct = new CFactory();
			
			fct.MethodBuild();
			
			fct.Show();
			
			
`<Referência>` : <https://refactoring.guru/pt-br/design-patterns>
