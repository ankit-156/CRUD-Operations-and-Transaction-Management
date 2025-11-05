
╔════════════════════════════════════════════════════════╗
║  SPRING & HIBERNATE COMPREHENSIVE DEMONSTRATION        ║
╚════════════════════════════════════════════════════════╝


============================================================
PART A: SPRING DEPENDENCY INJECTION (JAVA-BASED CONFIG)
============================================================
INFO: Refreshing org.springframework.context.annotation.AnnotationConfigApplicationContext
INFO: Overriding bean definition for bean 'course'
INFO: Creating shared instance of singleton bean 'springDIConfig'
INFO: Creating shared instance of singleton bean 'course'
INFO: Creating shared instance of singleton bean 'studentBean'

Student Name: John Doe
Roll Number: 12345
Course: Computer Science (Code: CS101)

INFO: Closing org.springframework.context.annotation.AnnotationConfigApplicationContext


============================================================
PART B: HIBERNATE CRUD OPERATIONS
============================================================
INFO: HHH000204: Processing PersistenceUnitInfo [name: default]
INFO: HHH000412: Hibernate Core {5.6.10.Final}
INFO: HCANN000001: Hibernate Commons Annotations {5.1.2.Final}
INFO: HHH000400: Using dialect: org.hibernate.dialect.MySQL8Dialect
INFO: HHH000490: Using JtaPlatform implementation: [org.hibernate.engine.transaction.jta.platform.internal.NoJtaPlatform]

1. CREATE - Adding Students...
Hibernate: 
    insert 
    into
        students
        (age, course, email, student_name) 
    values
        (?, ?, ?, ?)
Student saved successfully!

Hibernate: 
    insert 
    into
        students
        (age, course, email, student_name) 
    values
        (?, ?, ?, ?)
Student saved successfully!

2. READ - Fetching All Students...
Hibernate: 
    select
        student0_.student_id as student_1_2_,
        student0_.age as age2_2_,
        student0_.course as course3_2_,
        student0_.email as email4_2_,
        student0_.student_name as student_5_2_ 
    from
        students student0_

Student [ID=1, Name=Alice Johnson, Email=alice@example.com, Age=20, Course=Computer Science]
Student [ID=2, Name=Bob Smith, Email=bob@example.com, Age=22, Course=Mechanical Engineering]

3. UPDATE - Modifying Student...
Hibernate: 
    select
        student0_.student_id as student_1_2_0_,
        student0_.age as age2_2_0_,
        student0_.course as course3_2_0_,
        student0_.email as email4_2_0_,
        student0_.student_name as student_5_2_0_ 
    from
        students student0_ 
    where
        student0_.student_id=?

Hibernate: 
    update
        students 
    set
        age=?,
        course=?,
        email=?,
        student_name=? 
    where
        student_id=?
Student updated successfully!

4. READ - Fetching Single Student...
Hibernate: 
    select
        student0_.student_id as student_1_2_0_,
        student0_.age as age2_2_0_,
        student0_.course as course3_2_0_,
        student0_.email as email4_2_0_,
        student0_.student_name as student_5_2_0_ 
    from
        students student0_ 
    where
        student0_.student_id=?

Student [ID=1, Name=Alice Johnson, Email=alice@example.com, Age=21, Course=Software Engineering]

5. DELETE - Removing Student...
Hibernate: 
    select
        student0_.student_id as student_1_2_0_,
        student0_.age as age2_2_0_,
        student0_.course as course3_2_0_,
        student0_.email as email4_2_0_,
        student0_.student_name as student_5_2_0_ 
    from
        students student0_ 
    where
        student0_.student_id=?

Hibernate: 
    delete 
    from
        students 
    where
        student_id=?
Student deleted successfully!

6. Final Student List:
Hibernate: 
    select
        student0_.student_id as student_1_2_,
        student0_.age as age2_2_,
        student0_.course as course3_2_,
        student0_.email as email4_2_,
        student0_.student_name as student_5_2_ 
    from
        students student0_

Student [ID=1, Name=Alice Johnson, Email=alice@example.com, Age=21, Course=Software Engineering]


============================================================
PART C: SPRING + HIBERNATE TRANSACTION MANAGEMENT
============================================================
INFO: Refreshing org.springframework.context.annotation.AnnotationConfigApplicationContext
INFO: Creating shared instance of singleton bean 'springHibernateConfig'
INFO: Creating shared instance of singleton bean 'dataSource'
INFO: Creating shared instance of singleton bean 'sessionFactory'
INFO: Building JPA container EntityManagerFactory for persistence unit 'default'
INFO: HHH000204: Processing PersistenceUnitInfo [name: default]
INFO: HHH000412: Hibernate Core {5.6.10.Final}
INFO: HHH000400: Using dialect: org.hibernate.dialect.MySQL8Dialect
INFO: Creating shared instance of singleton bean 'transactionManager'
INFO: Creating shared instance of singleton bean 'bankingService'
INFO: Creating shared instance of singleton bean 'accountDAO'
INFO: Creating shared instance of singleton bean 'transactionDAO'

1. Creating Bank Accounts...
Hibernate: 
    insert 
    into
        accounts
        (account_number, balance, holder_name) 
    values
        (?, ?, ?)
Account created: Account [ID=1, Number=ACC001, Holder=John Doe, Balance=$5000.0]

Hibernate: 
    insert 
    into
        accounts
        (account_number, balance, holder_name) 
    values
        (?, ?, ?)
Account created: Account [ID=2, Number=ACC002, Holder=Jane Smith, Balance=$3000.0]

2. Initial Account Balances:
Hibernate: 
    select
        account0_.account_id as account_1_0_,
        account0_.account_number as account_2_0_,
        account0_.balance as balance3_0_,
        account0_.holder_name as holder_n4_0_ 
    from
        accounts account0_ 
    where
        account0_.account_number=?

Account [ID=1, Number=ACC001, Holder=John Doe, Balance=$5000.0]
Account [ID=2, Number=ACC002, Holder=Jane Smith, Balance=$3000.0]

3. Performing Successful Transfer...

=== Starting Money Transfer ===
From: ACC001 To: ACC002 Amount: $500.0

Hibernate: 
    select
        account0_.account_id as account_1_0_,
        account0_.account_number as account_2_0_,
        account0_.balance as balance3_0_,
        account0_.holder_name as holder_n4_0_ 
    from
        accounts account0_ 
    where
        account0_.account_number=?

Hibernate: 
    select
        account0_.account_id as account_1_0_,
        account0_.account_number as account_2_0_,
        account0_.balance as balance3_0_,
        account0_.holder_name as holder_n4_0_ 
    from
        accounts account0_ 
    where
        account0_.account_number=?

Deducting $500.0 from ACC001
Hibernate: 
    update
        accounts 
    set
        account_number=?,
        balance=?,
        holder_name=? 
    where
        account_id=?

Adding $500.0 to ACC002
Hibernate: 
    update
        accounts 
    set
        account_number=?,
        balance=?,
        holder_name=? 
    where
        account_id=?

Hibernate: 
    insert 
    into
        transactions
        (amount, from_account, status, to_account, transaction_date) 
    values
        (?, ?, ?, ?, ?)

Transaction completed successfully!
New balance of ACC001: $4500.0
New balance of ACC002: $3500.0

4. Final Account Balances:
Hibernate: 
    select
        account0_.account_id as account_1_0_,
        account0_.account_number as account_2_0_,
        account0_.balance as balance3_0_,
        account0_.holder_name as holder_n4_0_ 
    from
        accounts account0_ 
    where
        account0_.account_number=?

Account [ID=1, Number=ACC001, Holder=John Doe, Balance=$4500.0]
Account [ID=2, Number=ACC002, Holder=Jane Smith, Balance=$3500.0]

5. Testing Transaction Rollback (Insufficient Balance)...

=== Starting Money Transfer ===
From: ACC001 To: ACC002 Amount: $10000.0

Hibernate: 
    select
        account0_.account_id as account_1_0_,
        account0_.account_number as account_2_0_,
        account0_.balance as balance3_0_,
        account0_.holder_name as holder_n4_0_ 
    from
        accounts account0_ 
    where
        account0_.account_number=?

Hibernate: 
    select
        account0_.account_id as account_1_0_,
        account0_.account_number as account_2_0_,
        account0_.balance as balance3_0_,
        account0_.holder_name as holder_n4_0_ 
    from
        accounts account0_ 
    where
        account0_.account_number=?

❌ Transaction Failed: Insufficient balance in account: ACC001
✓ All changes have been rolled back!

6. Balances After Failed Transaction (Should be unchanged):
Hibernate: 
    select
        account0_.account_id as account_1_0_,
        account0_.account_number as account_2_0_,
        account0_.balance as balance3_0_,
        account0_.holder_name as holder_n4_0_ 
    from
        accounts account0_ 
    where
        account0_.account_number=?

Account [ID=1, Number=ACC001, Holder=John Doe, Balance=$4500.0]
Account [ID=2, Number=ACC002, Holder=Jane Smith, Balance=$3500.0]

INFO: Closing org.springframework.context.annotation.AnnotationConfigApplicationContext
INFO: HHH000030: Cleaning up connection pool [jdbc:mysql://localhost:3306/combined_db]

============================================================
ALL DEMONSTRATIONS COMPLETED SUCCESSFULLY!
============================================================

Process finished with exit code 0
