These are templates from http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/updating.stacks.walkthrough.html . However, the website doesn't change when I try it. Here is what I do:

  1. I create a stack with the template simple_orig.json
  2. I update it (console, direct updated, new template) with simple_upd.json
  3. I wait for UPDATE_COMPLETED, then more than 15 minutes, nothing happens. To investigate on the instance (see index.php, logs):
  4. I update with simple_key.json - this works fine
  5. I try again to update, with simple_key_upd.json - again, no success

On the instance, I found nothing in the logs. The cfn-hup log reports that it's alive, but didn't notice a change. When I ran "/opt/aws/bin/cfn-init -s arn:aws:cloudformation:us-east-1:030830401805:stack/suny-dev-tutorial-9/6c40f1d0-f369-11e6-9732-500c286e44d1 -r WebServerInstance  --region     us-east-1" manually, it worked. 

I one experiment (I did in in several regions, and several times), when I updated again with simple_key_upd_2.json , the first update was propagated. simple_key_upd_3.json was created to test the same with change sets. No luck.

From previous experiments with what I really want to do - see cloudformation_1nodeelk_cfnhup.yaml - I get the impression that (1) "big" changes are reliably detected (replacement of ec2 instances); (2) updates of files sometimes are detected hours later, if at all.

I'd be very grateful for an explanation of this mystery.

S. Kim
