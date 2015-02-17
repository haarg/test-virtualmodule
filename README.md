# Test::VirtualModule

Perl virtual modules mechanism for unit testing.

See example:

    # load virtual module
    use Test::VirtualModule qw/BlahBlahBlah::FooBar/;
    # import mocked module, it's ok
    use BlahBlahBlah::FooBar;
    # Mock constructor
    Test::VirtualModule->mock_sub('BlahBlahBlah::FooBar',
        new => sub {
            my $self = {};
            bless $self, 'BlahBlahBlah::FooBar';
            return $self;
        }
    );
    # create object
    my $object = BlahBlahBlah::FooBar->new();
    
