# Guice

public class BasicModule extends AbstractModule {
 
    @Override
    protected void configure() {
        bind(Communicator.class).to(DefaultCommunicatorImpl.class);
    }
}

instance of DefaultCommunicatorImpl is to be injected wherever a Communicator variable is found.

You can also inject a dependency that doesn't have a default no-arg constructor using constructor binding:

public class BasicModule extends AbstractModule {
 
    @Override
    protected void configure() {
        bind(Boolean.class).toInstance(true);
        bind(Communication.class).toConstructor(
          Communication.class.getConstructor(Boolean.TYPE));
}

As bindings are defined in Binding Module, Guice uses them whenever it needs to inject dependencies. In case bindings are not present, it can attempt to create just-in-time bindings. Bindings present in binding module are called explicit bindings and are of higher precedence whereas just-in-time bindings are called implicit bindings. If both type of bindings are present, explicit bindings are considered for mapping.

	Injectable Constructors						Non-private, No-argument constructors are eligible for just-in-time bindings. 
																		Another way is to annotate a constructor with @Inject annotation.
	@ImplementedBy annotation	        @ImplementedBy annotation tells the guice about the implementation class. 
																		No binding is required in Binding Module in such a case.
	@ProvidedBy annotation	          @ProvidedBy annotation tells the guice about the provider of implementation class. 
																		No binding is required in Binding Module in such a case.

	bind(Communicator.class).annotatedWith(Names.named("AnotherCommunicator"))
		.to(Communicator.class).in(Scopes.SINGLETON);
  
The in(Scopes.SINGLETON) specifies that any Communicator field with the @Named(“AnotherCommunicator”) 
will get a singleton injected. This singleton is lazily initiated by default.

Guice provides a way to create bindings with complex objects using @Provides annotation.

	@Provides
	public SpellChecker provideSpellChecker(){
		 String dbUrl = "jdbc:mysql://localhost:5326/emp";
		 String user = "user";
		 int timeout = 100;
		 SpellChecker SpellChecker = new SpellCheckerImpl(dbUrl, user, timeout);
		 return SpellChecker;
	}

	class TextEditor {
		 private SpellChecker spellChecker;
		 @Inject
		 public TextEditor( SpellChecker spellChecker) {
				this.spellChecker = spellChecker;
		 }
		 public void makeSpellCheck(){
				spellChecker.checkSpelling();
		 } 
	}

@provides method becomes more complex, these methods can be moved to seperate classes using Provider interface.

	class SpellCheckerProvider implements Provider<SpellChecker>{
		 @Override
		 public SpellChecker get() {
				String dbUrl = "jdbc:mysql://localhost:5326/emp";
				String user = "user";
				int timeout = 100;
				SpellChecker SpellChecker = new SpellCheckerImpl(dbUrl, user, timeout);
				return SpellChecker;
		 } 
	}
Next step is to map the provider to type.

	bind(SpellChecker.class).toProvider(SpellCheckerProvider.class);
