---
title: 'Connecting to Databend using BendSQL'
sidebar_label: 'Connecting to Databend'
---
import StepsWrap from '@site/src/components/StepsWrap';
import StepContent from '@site/src/components/Steps/step-content';

In this tutorial, we will guide you through the process of connecting to Databend using BendSQL as the user `root`.

<StepsWrap>
<StepContent number="0" title="Before You Start">

- Ensure that BendSQL is installed on your machine. See [Installing BendSQL](index.md#installing-bendsql) for instructions on how to install BendSQL using various package managers.
- Ensure that you have a local Databend instance ready for testing. See [Docker and Local Deployments](../../10-deploy/03-deploying-local.md) for detailed instructions. 
- In this tutorial, you will use the `root` account to connect to Databend. During deployment, uncomment the following lines in the [databend-query.toml](https://github.com/datafuselabs/databend/blob/main/scripts/distribution/configs/databend-query.toml) configuration file to select this account:

    ```sql title="databend-query.toml"
    [[query.users]]
    name = "root"
    auth_type = "no_password"
    ```

</StepContent>
<StepContent number="1" title="Launch BendSQL">

To launch BendSQL, enter `bendsql` directly into your terminal or command prompt.

:::note
The command `bendsql` launches and connects BendSQL to the local Databend at 127.0.0.1 using the `root` user without requiring a password. If you wish to connect to a local Databend with a different user, such as 'eric' with the password 'abc123', use the command `bendsql --user eric --password abc123`. To view all available arguments and their default values, type `bendsql --help`.
:::

![Alt text](/img/connect/bendsql-1.gif)


</StepContent>
<StepContent number="2" title="Execute Queries">

Once connected, you can execute SQL queries in the BendSQL shell. For instance, type `SELECT NOW();` to return the current time:

![Alt text](/img/connect/bendsql-2.gif)

</StepContent>
<StepContent number="3" title="Quit BendSQL">

To quit BendSQL, type `quit`.

![Alt text](/img/connect/bendsql-3.gif)

</StepContent>
</StepsWrap>