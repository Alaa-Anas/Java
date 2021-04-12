        final byte MONTHS_IN_YEARS = 12;
        final byte PERCENT = 100;

        Scanner scanner = new Scanner(System.in);

        System.out.print("Principle: ");
        int principle = scanner.nextInt();

        System.out.print("Annual Interest Rate:" );
        float annualInterest = scanner.nextFloat();
        float monthlyInterest = annualInterest / PERCENT / MONTHS_IN_YEARS;

        System.out.print("Period (Years): ");
        byte years = scanner.nextByte();
        int number_of_payments = years * MONTHS_IN_YEARS;

        double mortgage = principle
                * (monthlyInterest * Math.pow(1 + monthlyInterest, number_of_payments))
                / (Math.pow(1 + monthlyInterest, number_of_payments) - 1);

        String mortgageFormatted = NumberFormat.getCurrencyInstance().format(mortgage);
        System.out.println("Mortgage: " + mortgageFormatted);
