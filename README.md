public class Main
{
	public static void main(String[] args) {
		
        Scanner scanner = new Scanner(System.in);
        
        int[] assetModelYear = {2005, 2006, 2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017};
        int[] requiredLoanTenure = {1, 2, 3, 4, 5};
        int currentYear = 2024;
		
        int newEMIWithIDFCOnProposedVehicle = 15000;
        int otherFixedEMIExcCurrentProposedCarLoanEMI = 20000;
        int FixedEMIMonthlyIncNewEMI = newEMIWithIDFCOnProposedVehicle +otherFixedEMIExcCurrentProposedCarLoanEMI;
		
        System.out.println("FixedEMIMonthlyIncNewEMI = " + FixedEMIMonthlyIncNewEMI);
        float foir = 0.0f;
		
		if(selectedEmploymentType.equals("Salaried")){
           foir = fixedEMIMonthlyIncNewEMI / ((float) (salaryOrIncome /12));
        }else if (selectedEmploymentType.equals("Self Employed")) {
            foir = fixedEMIMonthlyIncNewEMI / ((float) (salaryOrIncome / 12) * 2.5f);
        }else {
            System.out.println("Invalid employment type selected.");
        }
        float foirPercent = foir * 100;
         
        System.out.println("FOIR (Fixed Obligations to Income Ratio): " + foirPercent + "%");
         
		System.out.println("Select employment type:");
        displayArray2(EmploymentType);
		
		String selectedEmploymentType = scanner.nextLine();

        System.out.println("Select asset model year:");
        displayArray(assetModelYear);

        int selectedModelYear = scanner.nextInt();

        System.out.println("Select required loan tenure (in years):");
        displayArray(requiredLoanTenure);

        int selectedLoanTenure = scanner.nextInt();

        int assetAgeEot = (currentYear - selectedModelYear) + selectedLoanTenure;

        System.out.println("Asset age at end of tenure: " + assetAgeEot);

        scanner.close();
    }

    // Utility method to display array elements
    public static void displayArray(int[] array) {
        for (int i = 0; i < array.length; i++) {
            System.out.print(array[i]);
            if (i < array.length - 1) {
                System.out.print(", ");
            }
        }
        System.out.println();
    }
	  public static void displayArray2(String[] array) {
        for (int i = 0; i < array.length; i++) {
            System.out.print(array[i]);
            if (i < array.length - 1) {
                System.out.print(", ");
            }
        }
        System.out.println();
    }
}

