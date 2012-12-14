# ResqueBundle

**Create a Job**

    <?php

    namespace ShonM\ResqueBundle\Jobs;

    use ShonM\ResqueBundle\Jobs\ContainerAwareJob;

    class EmptyJob extends ContainerAwareJob
    {
        public function perform ()
        {
            fwrite(STDOUT, "\x1B[31m" . 'Performing a job - Hello from EmptyJob!' . "\x1B[39m" . "\n");
        }
    }

**Post your Job**

```$container->get('resque')->add('ShonM\ResqueBundle\Jobs\EmptyJob', 'queuename', array('params'));```

**Hire some Workers**

```app/console resque:worker queuename```

**Party**