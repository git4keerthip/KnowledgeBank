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


bind(Communicator.class).annotatedWith(Names.named("AnotherCommunicator"))
  .to(Communicator.class).in(Scopes.SINGLETON);
  
The in(Scopes.SINGLETON) specifies that any Communicator field with the @Named(“AnotherCommunicator”) 
will get a singleton injected. This singleton is lazily initiated by default.
