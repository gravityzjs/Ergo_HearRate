import streamlit as st

st.set_page_config(page_title="Hello")
st.title("Calculation of AT/UT")
st.write("""**Training Heart Rate Range**\nTo determine your THRR you need to first determine the following values:\n - Maximum Heart Rate (MHR)\n- Resting Heart Rate (RHR)\n- Heart Rate Reserve (HRR)""")
st.divider()
st.write("**Notes:**")
st.markdown("MHR=205.8 - (0.685 * age) in following calculation")
st.markdown("RHR: To determine your RHR, take your pulse first thing in the morning, before engaging in any significant activity")
st.markdown("HRR = MHR - RHR")
st.markdown("""**Zone**  **Range**\n
            Details:\n
            UT2:  65-75% of HRR+ RHR\n
            UT1:  75-80% 0f HRR + RHR \n
            AT: 80-85% of HRR + RHR\n
            AN:  >85% """)

with st.form('keys'):
    st.write("Enter your personal data")
    age=st.text_input("Age")
    st.markdown("For HRH, you need to test it when you wake up in the morning")
    rhr=st.text_input("What is your RHR? Enter a number")
    button=st.form_submit_button("Submit to calculate your different Zone")
    
    
if button:
    mhr=205.8 - (0.685 * int(age))
    hrr=mhr-int(rhr)
    hrr_rhr=hrr+int(rhr)
    ut2=[round(0.65*hrr_rhr,2),round(0.75*hrr_rhr,2)]
    ut1=[round(0.75*hrr_rhr,2),round(0.8*hrr_rhr,2)]
    at=[round(0.8*hrr_rhr,2),round(0.85*hrr_rhr,2)]
    an=[round(0.85*hrr_rhr,2), "Your Max"]
    result={"Type":["Min","Max"],
            "UT2":ut2,
            "UT1":ut1,
            "AT":at,
            "AN":an}

    st.subheader("Result")
    st.dataframe(result)
    
    st.write("Try your best! You can do it!")
    st.markdown("---")
    st.markdown("Take a screenshot to save your results")
