def main():

    seats = {i: "Available" for i in range(1, 21)}

    #Specific rows
    FIRST_CLASS = [1, 2, 3, 4, 5]  # First 5 seats
    EMERGENCY_ROWS = [11, 12, 13, 14]  # Two rows (4 seats)

    print("=" * 40)
    print("      AIR CUBE BOOKING SYSTEM      ")
    print("=" * 40)

    while True:
        #Current seating status
        print("\n--- Current Seat Map ---")
        for i in range(1, 21):
            status = "[ ]" if seats[i] == "Available" else "[X]"
            print(f"Seat {i:02d}: {status}", end="\t" if i % 5 != 0 else "\n")

        print("\nOptions: Enter seat number(s) separated by commas (e.g., 1, 5, 12) or 'q' to quit.")
        user_input = input("Selection: ").strip()

        if user_input.lower() == 'q':
            print("Thank you for flying with us. Goodbye!")
            break

        #Process multiple seats if provided
        selected_seats = [s.strip() for s in user_input.split(',')]

        for seat_str in selected_seats:
            try:
                seat_num = int(seat_str)

                #Validation: Does seat exist?
                if seat_num not in seats:
                    print(f"ERROR: Seat {seat_num} does not exist on this plane.")
                    continue

                #Validation: Is seat already taken?
                if seats[seat_num] == "Taken":
                    print(f"ERROR: Seat {seat_num} is already taken. Please choose another.")
                    continue

                #Handle First-Class logic
                if seat_num in FIRST_CLASS:
                    print(f"--- Seat {seat_num} is FIRST CLASS. A selection fee applies. ---")

                #Handle Emergency Row logic
                if seat_num in EMERGENCY_ROWS:
                    print(f"!!! ATTENTION: Seat {seat_num} is in an EMERGENCY EXIT row. !!!")
                    confirm = input(
                        f"Do you accept responsibility to assist in an emergency for seat {seat_num}? (y/n): ")
                    if confirm.lower() != 'y':
                        print(f"Purchase for seat {seat_num} cancelled: Agreement required.")
                        continue

                # 5. Final
                seats[seat_num] = "Taken"
                print(f"SUCCESS: Seat {seat_num} has been assigned to you.")

            except ValueError:
                print(f"ERROR: '{seat_str}' is not a valid seat number.")


if __name__ == "__main__":
    main()
